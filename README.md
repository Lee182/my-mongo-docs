# my-mongo-docs
Docs on mongodb (db = database) logging or doc'ing what I've learnt or found so far
## Install
To install mongo check out the [install docs](http://docs.mongodb.org/master/installation/) and follow the instructions for your machine

#### For Debian install (I'm on elementaryOS!)

1. Register keys ```$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10```
2. Setup lsb-release 
  ```
  $ sudo apt-get install lsb-release
  $ echo "deb http://repo.mongodb.org/apt/debian "$(lsb_release -sc)"/mongodb-org/3.0 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list
  ```
3. 'apt-get' mongo ```$ sudo apt-get update```     ```$ sudo apt-get install -y mongodb-org```

##Intro
  <blockquote>"MongoDB is an open-source document database that provides high performance, high availability, and automatic scaling." [defined by mongo docs](http://docs.mongodb.org/master/core/introduction/)</blockquote>
### So why learn a database?
####First off why is data important? and what is data? 
Data I'd probably define as a model of objects that we interact with in world. So it could be quotes of shakepear from years ago, geneologies or historical entries, the amount of milk i have in the fridge, how often I login into facebook, order details and a shopping basket or temperature and wind direction for weather projections. Literally anything any human can express with words or structure can be modelled and collected togeather into a database.<em>The use cases are endless </em> <br />

Learning how to import, use and navigate and project data is a great skill to have. 
I hope to share with you or document what I have learnt as a beginner in respect to databases  
####Some database terms
- db : database
- Data mining : importing data from different sources (websites or text) and putting it into an standard format or schema within a db
- Schema : The set structure and type (String, Boolean, Number ...) of data in a entry wihin an collection <br / > note mongodb is schemaless and this gives it flexibility see later (schemaless)  
- CRUD : Create Read Update Delete, an acronmy for common db functions 

###SECTION NOT COMPLETE
mongo documents are similar to .json file format,
![json document](http://docs.mongodb.org/master/_images/crud-annotated-document.png)
MongoDB isn't like SQL and other relational databases (not like I know SQL or from am the SQL world), in which reams of data is stored in tables, with forign keys, and set schemas.
Rather data stored in a non-relational hierachy, and without schemas; so what does this mean
####non-relational hierachy
relational table
####Mongodb is has Embedded hierachy
Entries have like a json format, take if we were to model a blog page you could model each post as an document with an date and time and you could <strong>embed</strong> embed the comments within the post document. MAKE BLOG MODEL WIREFRAME Unlike SQL a releational database with data indexed to mulitple tables, data can be embedded within the posts object making it visually easilier to organize with pluses of less file space and faster read times
####Mongodb is Schemaless (without Schema)
A schema from the [database terms](####Some database terms) further up the page is the set structure or model of an object. Mongodb is schemaless, this doesn't mean a document doesn't have a structure or consistentcy it just means that the database is flexible, having new fields where they werern't before or different data types for the same field. 
Schemaless just means the database is free so to speak, and updating or merging/porting database is a lot easier
