---
root: true
name: Beego introduction
sort: 0
---

# What is Beego?

Beego is a HTTP framework for developing Go based web applications rapidly. It can be used for developing Web Apps, APIs, and other powerful backend services quickly. It's RESTful framework carries its insparation from other great frameworks like tornado, sinatra, and flask. In addtion, it sports some integrated Go features such as interfaces and structures.

## The architecture of Beego

Here is the architecture of Beego:

![](../images/architecture.png)

Beego is built upon 8 independent modules and loosely coupled. Beego is designed for modular programming. It's loosely coupled archictecture allows you to use all these modules without using Beego's HTTP logic. For example, you can use the cache module to handle your caching, you can use the logs module for logging, and you can use config module for processing files in many format. In addtion, you can use all these modules not only in Beego but also in many other applications such as socket games. This is one of the reasons that Beego is so popular. Like Legos, you should know all magnificent models are built using many small pieces. In the same philosophy, Beego modules are constructed using many small building, this is what gives Beego its power. We will talk about more about the modules later.

## The executing logic of Beego

Beego is based on these modules so what's its executing logic? Beego is
a typical MVC architecture. Here is its executing logic:

![](../images/flow.png)

## The project structure of Beego

Here is the folder of a typical Beego project:

```
├── conf
│   └── app.conf
├── controllers
│   ├── admin
│   └── default.go
├── main.go
├── models
│   └── models.go
├── static
│   ├── css
│   ├── ico
│   ├── img
│   └── js
└── views
    ├── admin
    └── index.tpl
```

We can see the M (models), V (views), C (controllers) folders. `main.go` is the starting file.

>You can use [bee tool to create a new project](../install/bee.md).
