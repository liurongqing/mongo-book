# 查询

> 文档：<https://www.mongodb.com/docs/manual/tutorial/query-documents/>

## 查询方法

`db.collection.find()`

`db.collection.findOne()`

## 查询一条数据

```bash
db.inventory.findOne({ _id: "id001" })
```

## 查询多条数据

```bash
db.inventory.find({ name: "001" })
```
