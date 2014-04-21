---
name: Filters
sort: 2
---

# Filters

Beego supports custom filter middlewares. E.g.: user authentication and force redirecton.

Here is an example of a filter function:

	beego.InsertFilter(pattern string, pos int, filter FilterFunc)
	
Here is the FilterFunc signature:

	type FilterFunc func(*context.Context)

InsertFilter's three params:

<<<<<<< HEAD
- pattern: router rules. It can route based on the rules. Use `*` to match all.
- action: the place to execute Filter. There are four fixed params. They represent different execution process.
  - BeforeRouter: before finding router.
	- AfterStatic: after static rendering.
	- BeforeExec: After finding router and before executing the matched Controller.
	- AfterExec: After executing Controller.
=======
- pattern: router rules. It can router based on the rules. Use `*` to match all.
- pos: the place to execute Filter. There are five fixed params. They represent different execution process.
 	- beego.BeforeRouter: before finding router.
	- beego.AfterStatic: after static rendering.
	- beego.BeforeExec: After finding router and before executing the matched Controller.
	- beego.AfterExec: After executing Controller.
	- beego.FinishRouter: After finishing router.
>>>>>>> upstream/master
- filter: filter function type FilterFunc func(*context.Context)


Here is the example to authenticate if the user is logged in for all requests:

```go
var FilterUser = func(ctx *context.Context) {
    _, ok := ctx.Input.Session("uid").(int)
    if !ok {
        ctx.Redirect(302, "/login")
    }
}

beego.InsertFilter("*", beego.AfterStatic, FilterUser)
```

>>>One thing you need to care about is he Filter useing session must use after `AfterStatic` because session is not initialized before it.


You can run the Filters by matching regex router rules:

```go
var FilterUser = func(ctx *context.Context) {
    _, ok := ctx.Input.Session("uid").(int)
    if !ok {
        ctx.Redirect(302, "/login")
    }
}
beego.InsertFilter("/user/:id([0-9]+)", beego.AfterStatic, FilterUser)
```
## Filter Implementation UrlManager
Context.Input has new feature `RunController` and `RunMethod` from beego1.1.2. So we can controller the router in our filter and skip the beego's router rule.

For example:

```go
var UrlManager = func(ctx *context.Context) {
    //read urlMapping data from database
	urlMapping := model.GetUrlMapping()
	for baseurl,rule:= urlMapping {
		if baseurl == ctx.Request.RequestURI {
			ctx.Input.RunController = rule.controller
			ctx.Input.RunMethod = rule.method		
			break				
		}
	}
}

beego.AddFilter("*","AfterStatic",UrlManager)
```
