# 更新

> 文档：<https://www.mongodb.com/docs/manual/tutorial/update-documents/>

## 更新方法

`db.collection.updateOne()` 更新一条

`db.collection.updateMany()` 更新多条

`db.collection.replaceOne()` 替换一条

`db.collection.findOneAndUpdate()` 查询一条并更新

`db.collection.findOneAndReplace()` 查询一条并替换

`db.collection.bulkWrite()` 
> 一组操作，可以是：  
> `insertOne`、`deleteOne`、`updateOne`、`deleteMany`、`updateMany`、`replaceOne`


## updateOne

```bash
# `$set` 设置数据
# `$currentDate` 将 lastModified 字段设置为当前时间
db.inventory.updateOne(
  { _id: "fb100" },
  {
    $set: { name: "xx03" },
    $currentDate: { lastModified: true }
  }
)
```

## updateMany

```bash
# `$set` 设置数据
# `$currentDate` 将 lastModified 字段设置为当前时间
db.inventory.updateMany(
  { age: { $lt: 18 } },
  {
    $set: { name: "xx03" },
    $currentDate: { lastModified: true }
  }
)
```

## replaceOne

```bash
db.inventory.replaceOne(
  { name: "xx" },
  { name: "xx1", age: 20 }
)
```

## findOneAndUpdate

```bash
# 返回原始文档，返回 _id 与 name 字段
db.inventory.findOneAndUpdate(
  { name: "xx" },
  { $inc: { "age": 5 } },
  { projection: { "name": 1 }}
)
```

## findOneAndReplace

```bash
# 返回原始文档
db.inventory.findOneAndReplace(
  { name: "xx" },
  { name: "xx1", age: 20 },
  { sort: { "age": 1 }}
)
```

## bulkWrite

```bash
# 批量操作
db.pizzas.bulkWrite( [
  { insertOne: { document: { _id: 3, type: "beef" } } },
  { insertOne: { document: { _id: 4, type: "sausage" } } },
  { updateOne: {
      filter: { type: "cheese" },
      update: { $set: { price: 8 } }
  } },
  { deleteOne: { filter: { type: "pepperoni"} } },
  { replaceOne: {
      filter: { type: "vegan" },
      replacement: { type: "tofu", size: "small", price: 4 }
  } }
] )
```

## 其他

当 `updateOne()`、`updateMany()`、`replaceOne()` 选项配置为 `upsert: true` 时， 没有找到更新数据时，则插入数据
