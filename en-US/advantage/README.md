---
root: true
name: Advanced Beego
sort: 6
---

# Advanced Beego

We have demonstrated the basic use of Beego. Now we will talk about more about some advanced topics and features.

- [The In Process Monitor](./monitor.md)

  By default, Beego will serve out of two ports. The main port is 8080 for application to serve users. Another is 8088, to moniter the applicaitons internal process status, execution of tasks, and other stuff.

- [Filters](./filter.md)

  Filters is a very convenient feature for you to extend your logic. Through use of Filters you can easily implement extended functionality like user authentication, log visiting, compatibility switching and so on.

- [Reload](./reload.md)

  Automatic "reload" is always mentioned in web development, this Beego feature allows "HOT" deployment of your application without interuption of user requests.

>>> Please note: This feature is still in active development and is not consided "done" yet. It hase only tesed on Mac and Linux. In addtion, it hasn't been tested on production evnironment yet. Although this feature is worth mentioning, it is still under active development and testing.  Use of automatic application reloading is considered beta code so please be advised that you using it at your own risk.  For production environments, we recommended you use upstream of nginx, as a reverse proxy.
