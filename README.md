# Data+ Development Kit
### A starter pack for basic development.

***

Introduction
---

This is a basic [Docker](https://www.docker.com) and [Docker Compose](https://docs.docker.com/compose/) setup for testing and basic development.

I'm building this originally for the [Data+](https://bigdata.duke.edu/data) project, but will probably end up using it for a lot of experiments and one/offs.


Included Features
---

This builds a few different Docker containers, links them up, and makes it easy to try things and reset it quickly. From there you can take pieces and deploy them from there.

- Ruby 2.5.1
  - Gems:
    - Rails 5.2 (Web Development Framework)
    - Postgres (Postgres Bindings)
    - MySQL2 (MySQL Bindings)
    - Nokogiri (HTML Parser)
    - Puma (Development and Production Server)
- Python 3.6.5
- Node 9.11.1
- Yarn 1.5.1
- Python 2.7.15rc1
- MySQL 8.0.11
- Postgres 10.4

Docker Installation
---
### MacOS: 

You can find installation instructions for Docker at https://docs.docker.com/docker-for-mac/install/

Docker Compose (also needed for this project) comes preinstalled.

### Windows

So, there's a hiccup here. If you're already using Vagrant the method laid out below will break that. That's probably not good. If you're using Vagrant as well you want to follow these instructions: https://docs.docker.com/toolbox/overview/

For Windows 10 without Vagrant, follow these:
https://docs.docker.com/docker-for-windows/install/

Set Up
---
1. On GitHub, navigate to the **** repository.
1. In the top-right corner of the page, click Fork. This will make a copy of this for you to start with.
1. Clone your new repository ```git clone ****```
1. From the command line go to your new repository
1. Build all the containers ```docker-compose build --no-cache```

Usage
---

The most important part to remember is that the containers are ephemeral, but the volumes that are mounted retain data. What this means in practice is that, more or less, everything you do in the directory where the containers are launched from will appear in your machine.

This means you can create new folders, new projects etc. in the main folder and then run the commands from within the containers. Once you have everything set up you can then make whatever kick off command you want open when the containers are launched.

This lets you edit the files without worrying about clutter in your personal machine. Unlike something like Vagrant though machine changes (such as configuration variables) are not retained. This is usually a good thing, and if you need to adjust it then the Dockerfile should be edited so that the changes are made at start.

### Basic Commands

**Start Up To Command Line** 
_Use this for initial testing and development._

```
docker-compose run web /bin/bash
```

**Start Up All Containers** 
_Once you have a framework set up or you're ready to deploy a script you've set as the startup._

```
docker-compose up
```

**Start Up All Containers In The Background** _Same as above but daemonizes it to the background._

```
docker-compose up -d
```

**Shutdown All Containers** _Stop all containers and removes them. Do this at the end of the day or if you're working on the configuration files._

```
docker-compose down
```

Contact Information
---
If you have questions feel free to reach out, the documentation will be getting better

Christopher Guess
[cguess@gmail.com](cguess@gmail.com)
Twitter: [@CGuess](https://www.twitter.com/cguess)
PGP: https://keybase.io/cguess


