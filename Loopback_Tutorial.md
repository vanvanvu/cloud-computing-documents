Loopback Tutorial
============

## Structure
* [The LoopBack framework](http://loopback.io/doc/en/lb2/index.html)


## Install

* [Reference](https://strongloop.com/strongblog/install-node-js-loopback-and-strongops-on-digital-ocean/)

### Step 1: Installing NodeJs
```
$ sudo apt-get update
$ sudo apt-get install python-software-properties python g++ make
$ sudo add-apt-repository ppa:chris-lea/node.js
$ sudo apt-get update
$ sudo apt-get install nodejs
```
### Step 2: Installing Strongloop Framework
```
npm install -g strongloop
```
### Step 3: Installing library for Loopback models
```
npm install --save <name_of_package>
```

#### Loopback connectors
**Database connectors**

    Cloudant connector
    DashDB
    DB2 connector
    DB2 for z/OS
    Informix
    Memory connector
    MongoDB connector: loopback-connector-mongodb
    MySQL connector
    Oracle connector
    PostgreSQL connector
    Redis connector
    SQL Server connector
    SQLite3
    Elasticsearch connector: loopback-connector-elastic-search / loopback-connector-es

**Other connectors**

    Email connector
    Push connector
    Remote connector
    REST connector
    SOAP connector
    Storage connector
    Swagger connector

## Loopback Connector MongoDB
[MongoDB Connector Tutorial](https://loopback.io/doc/en/lb2/Connecting-to-MongoDB.html#create-a-data-source)

## Loopback Connector Elasticsearch
* [Loopback Connector Es](https://npm.proxy.ustclug.org/package/@atelierfabien/loopback-connector-es)
