---
name: Stand alone Deploy
sort: 1
---

# Standalone Deploy

This will run application at backend as a deamon.

## Linux

In Linux we can use `nohup` command to run application at backend:

	nohup ./beepkg &

Your application is running in the keep process of Linux.

## Windows

In Windows, set to auto running at backend on start. Two ways to do that:

1. Create a bat file and put it into "Run"
2. Create a service
