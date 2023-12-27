# 插入

> 文档：<https://www.mongodb.com/docs/manual/tutorial/insert-documents/>

## 插入方法

`db.collection.insertOne()` 插入一条

`db.collection.insertMany()` 插入多条

`db.collection.updateOne()`  与 `upsert: true` 一起使用

`db.collection.updateMany()` 与 `upsert: true` 一起使用

`db.collection.findAndModify()` 与 `upsert: true` 一起使用

`db.collection.findOneAndUpdate()` 与 `upsert: true` 一起使用

`db.collection.findOneAndReplace()` 与 `upsert: true` 一起使用

`db.collection.bulkWrite()` 与 `upsert: true` 一起使用

## insertOne

```bash
db.inventory.insertOne({ name: "xx" })
```

## insertMany

```bash
db.inventory.insertMany([{ name: "xx" }, { name: "xx2" }])
```
