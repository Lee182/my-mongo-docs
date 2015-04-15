# my-mongo-docs
Docs on mongodb recording what I've learnt so far
## Installation
To install mongo check out the [install docs](http://docs.mongodb.org/master/installation/) and follow the instructions for your machine

#### For Debian install (I'm on elementaryOS!)

1. Register keys ```$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10```
2. Setup lsb-release 
```
$ sudo apt-get install lsb-release
$ echo "deb http://repo.mongodb.org/apt/debian "$(lsb_release -sc)"/mongodb-org/3.0 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list
```
3. 'apt-get' mongo ```$ sudo apt-get update```     ```$ sudo apt-get install -y mongodb-org```
