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

##Introduction
  <i>"MongoDB is an open-source document database that provides high performance, high availability, and automatic scaling." [docs](http://docs.mongodb.org/master/core/introduction/)</i>
<br>
###SECTION NOT COMPLETE
mongo documents are similar to .json file format,
![json document](http://docs.mongodb.org/master/_images/crud-annotated-document.png)
MongoDB isn't like SQL and other relational databases (not like I know SQL or from am the SQL world), in which reams of data is stored in tables, with forign keys, and set schemas.
Rather data stored in a non-relational hierachy, and without schemas; so what does this mean
####non-relational hierachy
relational table                   
