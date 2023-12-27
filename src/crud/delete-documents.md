# 删除

> 文档：<https://www.mongodb.com/docs/manual/tutorial/remove-documents/>

## 删除方法

`db.collection.deleteOne()` 删除一条

`db.collection.deleteMany()` 删除指定过滤器匹配的所有文档

`db.collection.remove()` 删除一条或指定过滤器匹配的所有文档

`db.collection.findOneAndDelete()` 删除一条

`db.collection.findAndModify()` 删除一条

## deleteOne

```bash
db.inventory.deleteOne({ status: 0 })
```

## deleteMany

```bash
db.inventory.deleteMany({ status: 0 })
```

## remove

```bash
# justOne: true 则只删除一条
db.inventory.remove({ status: 0 }, { justOne: true })
```

## findOneAndDelete

```bash
# justOne: true 则只删除一条
# 返回删除的原始文档
db.inventory.findOneAndDelete({ status: 0 }, { sort: { "age": 1 } })
```

## findAndModify

```bash
# 排序与删除
db.people.findAndModify(
   {
     query: { status: 0 },
     sort: { rating: 1 },
     remove: true
   }
)
```
