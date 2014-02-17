---
root: true
name: Advanced Beego
sort: 6
---

# Advanced Beego

Now that we have demonstrated the basic use of Beego. Let's talk about some more advanced topics and features.

- [The In Process Monitor](./monitor.md)

  By default, Beego will open and serve out of two ports, an applicaiton service port and appliction monitoring port. Port 8080 is used as the main application service port your app will use to serve users. Another is port 8088, this port is used to moniter the applicaiton's internal process status, execution of tasks, and other interersting stuff.

- [Filters](./filter.md)

  Filters is a very convenient and powerful feature for you to extend your logic. Through use of Filters you can easily implement extended functionality like user authentication, log visiting, compatibility switching and so on.

- [Reload](./reload.md)

  Automatic "reload" is always mentioned in web development, this Beego feature allows "HOT" deployment of your application without interuption of user requests.

>>> Please note: This feature is still in active development and is not consided "done" yet. It hase only tesed on Mac and Linux. In addtion, it hasn't been tested on production evnironment yet. Although this feature is worth mentioning, it is still under active development and testing.  Use of automatic application reloading is considered beta code so please be advised that you using it at your own risk.  For production environments, we recommended you use upstream of nginx, as a reverse proxy.
