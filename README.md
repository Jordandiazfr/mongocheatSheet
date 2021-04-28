# Mongo DB CheatSheet

#### List all databases 
`show dbs`

### Drop a database

`db.dropDatabase()`

#### Use a database 
`use "database name" `

### Show all the collections 
`show collections`

### Create Collection 
`db.createCollection('Collection-Name')`

# CRUD OPERATIONS


### Create a row 

`db.<CollectionName>.insert({Object})`


`db.<CollectionName>.insertMany()`

### Read a collection

`db.<CollectionName>.find()`

##### Read with limit

`db.<collectionname>.find().limit(5).pretty()`

##### Read with a condition

`db.collection.find({ "var" : "value" })`

##### Counting rows

`db.<collectionname>.find().count()`

``

##### Sorting rows 

 ` db.posts.find().sort()`
 
 *Ascending* 
 
 ` db.people.find( { status: "A" } ).sort( { user_id: 1 } )`
 
 *Descending*

 ` db.people.find( { status: "A" } ).sort( { user_id: -1 } )`
 
 
##### Greater & Less Than

```
db.<collectionname>.find({ <onekey>: { $gt: 2 } })
db.<collectionname>.find({ <onekey>: { $gte: 7 } })
db.<collectionname>.find({ <onekey>: { $lt: 7 } })
db.<collectionname>.find({ <onekey>: { $lte: 7 } })
```
 

### Delete a collection

`db.<collectionname>.drop()`

`db.<collectioname>.remove({Object to remove})` or  

`db.<collectioname>.remove({})` 


## Install MongoDB Server in Ubuntu 18.04 Bionic


`wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -`

```echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list```


`sudo apt-get update`

`sudo apt-get install -y mongodb-org`

`sudo systemctl start mongod (to start MONGO)`

`sudo systemctl status mongod (to see if it's running indeed)`

`mongo (to use mongo shell)`

`sudo systemctl stop mongod (to stop MONGO)`

###################
CHANGING CONFIGURATION SETTING

sudo vim /etc/mongod.conf
    bind_ip:0.0.0.0

sudo service mongod restart
