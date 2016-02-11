# MongoDB-test.md


D:\Software\MongoDB 3.0.2\bin>mongo.exe
MongoDB shell version: 3.0.2
connecting to: test
> mongoimport --db test --collection restaurants --drop --file primer-dataset.js
on
2016-02-11T08:54:29.706-0500 E QUERY    SyntaxError: Unexpected identifier
> use test
switched to db test
> show databases
local  0.078GB
> mongoimport --db test --collection restaurants --drop --file E:\MongoDB\primer
-dataset.json
2016-02-11T08:56:02.285-0500 E QUERY    SyntaxError: Unexpected identifier
> db.inventory.insert(
...    {
...      item: "ABC1",
...      details: {
...         model: "14Q3",
...         manufacturer: "XYZ Company"
...      },
...      stock: [ { size: "S", qty: 25 }, { size: "M", qty: 50 } ],
...      category: "clothing"
...    }
... )
WriteResult({ "nInserted" : 1 })
> db.inventory.find()
{ "_id" : ObjectId("56bc9359a079c10f48c3bcf9"), "item" : "ABC1", "details" : { "
model" : "14Q3", "manufacturer" : "XYZ Company" }, "stock" : [ { "size" : "S", "
qty" : 25 }, { "size" : "M", "qty" : 50 } ], "category" : "clothing" }
> var mydocuments =
...     [
...       {
...         item: "ABC2",
...         details: { model: "14Q3", manufacturer: "M1 Corporation" },
...         stock: [ { size: "M", qty: 50 } ],
...         category: "clothing"
...       },
...       {
...         item: "MNO2",
...         details: { model: "14Q3", manufacturer: "ABC Company" },
...         stock: [ { size: "S", qty: 5 }, { size: "M", qty: 5 }, { size: "L",
qty: 1 } ],
...         category: "clothing"
...       },
...       {
...         item: "IJK2",
...         details: { model: "14Q2", manufacturer: "M5 Corporation" },
...         stock: [ { size: "S", qty: 5 }, { size: "L", qty: 1 } ],
...         category: "houseware"
...       }
...     ];
> db.inventory.insert( mydocuments );
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 3,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
> db.inventory.find( {} )
{ "_id" : ObjectId("56bc9359a079c10f48c3bcf9"), "item" : "ABC1", "details" : { "
model" : "14Q3", "manufacturer" : "XYZ Company" }, "stock" : [ { "size" : "S", "
qty" : 25 }, { "size" : "M", "qty" : 50 } ], "category" : "clothing" }
{ "_id" : ObjectId("56bc93a8a079c10f48c3bcfa"), "item" : "ABC2", "details" : { "
model" : "14Q3", "manufacturer" : "M1 Corporation" }, "stock" : [ { "size" : "M"
, "qty" : 50 } ], "category" : "clothing" }
{ "_id" : ObjectId("56bc93a8a079c10f48c3bcfb"), "item" : "MNO2", "details" : { "
model" : "14Q3", "manufacturer" : "ABC Company" }, "stock" : [ { "size" : "S", "
qty" : 5 }, { "size" : "M", "qty" : 5 }, { "size" : "L", "qty" : 1 } ], "categor
y" : "clothing" }
{ "_id" : ObjectId("56bc93a8a079c10f48c3bcfc"), "item" : "IJK2", "details" : { "
model" : "14Q2", "manufacturer" : "M5 Corporation" }, "stock" : [ { "size" : "S"
, "qty" : 5 }, { "size" : "L", "qty" : 1 } ], "category" : "houseware" }
> db.inventory.find( { type: "snacks" } )
>
