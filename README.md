# my-mongo-docs
Docs on mongodb (db = database) logging or doc'ing what I've learnt or found so far
## Install
To install mongo check out the [install docs](http://docs.mongodb.org/master/installation/) and follow the instructions for your machine

#### For Debian install (I'm on elementaryOS!)

1. Register keys ```$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10```
2.
  ```
   $ sudo apt-get install lsb-release
   $ echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/stable multiverse #mongodb" | sudo    tee /etc/apt/sources.list.d/mongodb-org-3.0.list
  ```
3. 'apt-get' mongo ```$ sudo apt-get update && apt-get install -y mongodb-org```

##Intro
  <blockquote>"MongoDB is an open-source document database that provides high performance, high availability, and automatic scaling." [mongodb docs](http://docs.mongodb.org/master/core/introduction/)</blockquote>
### So why learn a database?
####First off why is data important? and what is data? 
Data, its all around us,  computer data could be defined as a model of objects, in the constraists of datatypes, ([datatypes accepted by our db](http://docs.mongodb.org/master/reference/bson-types/)),that we interact with in world. Data could be quotes of shakepear from years ago, geneologies or historical entries, the amount of milk i have in the fridge, how often I login into facebook, order details and a shopping basket or temperature and wind direction for weather projections. Literally anything any human can express with words or structure that can be modelled and collected togeather into a database

Learning how to import, use and navigate and project data is a great skill to have. 
I hope to share with you or document what I have learnt as a beginner in respect to databases  
####Some database terms
- db : database
- Data mining : importing data from different sources (websites or text) and putting it into an standard format or schema within a db
- Schema : The set structure and type (String, Boolean, Number ...) of data in a entry wihin an collection <br / > note mongodb is schemaless and this gives it flexibility see later (schemaless)  
- CRUD : Create Read Update Delete, an acronmy for common db functions 

So Whats good about mongo

###JSON like documents
mongo documents are similar to .json file format,
![json document](http://docs.mongodb.org/master/_images/crud-annotated-document.png)
MongoDB isn't like SQL and other relational databases as being reams of tables linking to one anothor and which have almost fixed table headers also known as set schemas.
Rather data stored in a non-relational hierachy, and without schemas; so what does this mean
####non-relational hierachy
so heres a relational table
<br>
![](http://www.databasedev.co.uk/image/activities_students.gif)
<br>
So remodelling this for an entry for John
```js
{
  _id: 84,
  name: "John Smith",
  activitys: [
    {name: "Tennis", cost:36},
    {name: "Swimming", cost: 15}
  ]
}
```
Notice how theres no activity1 cost1 but are both denoted by the array at the activitys property
<br>
So now lets put this data in to our database
#### starting our local server
First you want to make sure your server is running, to do this by 
  1. ` $ mongod -port 27017 ` note ` $ mongod` will do the same the default port is 27017 btw
  2. or to start on your linux machine by ` sudo restart mongod ` 

There are also options to change the db path and storage engine by the `--storageEngine mmapv1` `--dbpath /data/db` 
<>
#### connecting to our server
in the command line you can type ` $ mongo ` and this will connect us to the default port at 27017
<br>
```
MongoDB shell version: 3.0.3
connecting to: test
> 
```
notice you'll get a prompt like this, it is an interactive javascript shell which talks to our server, 'test' is the name of db we are using to see others do 
``` > show dbs ```
#### Making our first collection

####able te embed data
Entries have like a json format, take if we were to model a blog page you could model each post as an document with an date and time and you could <strong>embed</strong> embed the comments within the post document. MAKE BLOG MODEL WIREFRAME Unlike SQL a releational database with data indexed to mulitple tables, data can be embedded within the posts object making it visually easilier to organize with pluses of less file space and faster read times
####Mongodb is Schemaless (without Schema)
A schema from the [database terms](####Some database terms) further up the page is the set structure or model of an object. Mongodb is schemaless, this doesn't mean a document doesn't have a structure or consistentcy it just means that the database is flexible, having new fields where they werern't before or different data types for the same field. 
Schemaless just means the database is free so to speak, and updating or merging/porting database is a lot easier
