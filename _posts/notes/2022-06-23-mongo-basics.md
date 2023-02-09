---
title: "MongoDB Commands"
date: 2022-06-23
draft: false
tags: ["mongo", "cheatsheet", "database"]
categories: [database]
---


### Mongo Shell

- To run mongo shell from terminal:

```shell
$ mongosh
```

### Cheatsheet of basic commands
```shell
# show database:
> show dbs

# create database:
> use testDB

# drop database
> use testDB
> db.dropDatabase()

# use database
> use testDB

# show active db
> db

# show "tables" from active db
> show collections

# Insert into Collection
> db.user.insert({
        name: 'Mike',
        address: 'Canada'
    })

# Insert many into Collection
> db.user.insertMany([
    {
        name: 'Mike',
        address: 'Canada'
    },
    {
        name: 'Besh',
        address: 'Brazil'
    },
    {
        name: 'Nesh',
        address: 'USA'
    }
])

# Show all records
> db.user.find()

# Count the number of documents
> db.user.count()

# Pretty print
> db.user.find().pretty()

# Find something (where) clause:
# SQL EQUIVALENT
# SELECT * FROM user WHERE address = "Brazil";
> db.user.find({"address": "Brazil"}).pretty()

# AND / OR Conditions

# AND
> db.inventory.find({"status": "P"})

# OR
> db.inventory.find({$or: [{"status": "A"}, {"status": "P"}]})

# IN
> db.inventory.find({ "status": { $in: ["A", "P"] }}, {"status": 1})

# Delete all Documents from a Collection
> db.inventory.deleteMany({})

# Update single document
# Note: If there are multiple results, updateOne will only update the latest document.
> db.inventory.updateOne(
    { item: "paper" },
    { $set: { "size.uom": "in", status: "K" } }
)

# Update many
# Note: Even if there are multiple results, this will update all records
> db.inventory.updateMany(
    { item: "paper" },
    { $set: { "size.uom": "in", status: "K" } }
)

# Delete One
# Note: If there are multiple results, deleteOne will only delete the latest document.
> db.inventory.deleteOne({ "item": "paper" })

# Delete many
# Note: This deletes all the matching records.
> db.inventory.deleteMany({"status": "A"})
```

### RDBMS Equivalents

| RDBMS   | MongoDB     |
| ------- | --------    |
| Row     | Documents   |
| Table   | Collections |


---

### Queries

```shell
# Ordering of the results (1 - Asc, -1 Desc)
> db.inventory.find({}).sort({ qty: -1 })

# Query nested documents
# Note: ORDER MATTERS, if the order doesn't match filter will not work.
> db.inventory.find({ size: { h: 14, w: 21, uom: "cm" } })

# Query Nested fields
> db.inventory.find({"size.uom": "in"})
> db.inventory.find({"size.h": { $gt: 20 }})

# Query an array
# Note: ORDER MATTERS, if the order of tags are different, result will vary.
> db.inventory.find({ tags: ["red", "blank"] })

# Query with all
# Note: Querying with $all, provides all the results belonging to red and blank tag.
> db.inventory.find({ tags: { $all: ["red", "blank"] } })

# Query with :
# Note: Provides all the tags which belongs to red
> db.inventory.find({ tags: "red" })

# Query the elements in array with $gt / $lt
> db.inventory.find({ dim_cm: { $gt: 15 } })

# Query array with $elemMatch, match all the elements of array with given query
> db.inventory.find({ dim_cm: { $elemMatch: {$gt: 15, $lt: 20} } })

# Query with indexing elements
> db.inventory.find({"dim_cm.0": {$gt: 15}})
> db.inventory.find({"dim_cm.1": {$lt: 20}})

# Query by the size of array
> db.inventory.find({"dim_cm": {$size: 2}})
> db.inventory.find({"tags": {$size: 3}})
> db.inventory.find({"tags": {$size: 1}})

# Querying with Nested Dict within Array

# Finding the exact match of dict within array
> db.inventory.find({ instock: { warehouse: "A" } })
# Result: None

> db.inventory.find({ instock: { warehouse: "A", qty: 5 } })
# Result 1 with output

> db.inventory.find({ instock: { qty: 5, warehouse: "A" } })
# Result: None
# Note: Exact query match within the result will only provides the desired output

# Match the specific elements
# Match all
> db.inventory.find( { "instock.qty": { $lte: 20 } } )

# Match with the first element of array
> db.inventory.find( { "instock.0.qty": { $lte: 20 } } )

# Match with the second element of array
> db.inventory.find( { "instock.1.qty": { $lte: 20 } } )

# Note: All these 3 match will result in different results based on the array index you're querying

# Specifying multiple conditions in one field
# Matches all the
> db.inventory.find({ "instock.qty": 5, "instock.warehouse": "A" })

# Match exact
> db.inventory.find({ instock: {$elemMatch: {qty: 5, warehouse: "A"}} })
```

#### Querying NULL, EXISTS

```shell
db.inventory.insertMany([
    { _id: 1, item: null },
    { _id: 2 }
])

# Results in both empty results with null item and no item.
> db.inventory.find({ item: null })
# Result:
# { _id: 1, item: null }
# { _id: 2 }

Query with TYPE numbers:
$10 -> null

> db.inventory.find({ item: {$type: 10} })
# Result : { _id: 1, item: null }

> db.inventory.find({ item: {$exists: false} })
# Result: { "_id": 2 }


# Selecting certain fields only
> db.inventory.find({ status: "A" }, {_id: 0})

# Nested Fields
> db.inventory.find({ status: "A" }, { item: 1, status: 1, "size.uom": 1 })
db.inventory.find({
    qty: {$gte: 50},
    $or: [{status: "A"}, {status: "B"}],
    status: '',
    aother: []
})
```
