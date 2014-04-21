---
root: true
name: Advanced Beego
sort: 6
---

# Advanced Beego

Now that we have demonstrated the basics of Beego. Let's talk through some more advanced topics and features that the Beego framework offers:

- [The In Process Monitor](./monitor.md)

  By default, Beego will open and serve an applicaiton using two ports, an applicaiton service port and appliction monitoring port. Port 8080 is used as the main application service port your app will use to serve users. Another is port 8088, this port is used to moniter the applicaiton's internal process status, execution of tasks, and other interersting stuff.

- [Filters](./filter.md)

  Filters are a very convenient and powerful way to extend your application logic. Using Filters, you can easily implement extended functionality like user authentication, log visiting, compatibility switching and more.

- [Reload](./reload.md)

  Automatic "reload" is always mentioned in web development, this Beego feature allows "HOT" deployment of your application without interuption of user requests.

>>> Please note: This feature is still in active development and is not consided "production" ready yet. It has only tesed on Mac and Linux. In addtion, it hasn't been tested on production evnironments yet. Although this feature is worth mentioning, please know that this Beego feature is still under active development and testing.  Please be advised that you using it at your own risk.  For production environments, we recommended you use upstream of nginx, as a reverse proxy.
