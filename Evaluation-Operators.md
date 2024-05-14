# Evaluation Query Operators
#### regex:
```sql
db.collection.find({ field: { $regex: /^A/ } })
```

#### $jsonSchema:
```sql
db.collection.find({
  $jsonSchema: {
    required: ["name", "age"],
    properties: {
      name: { type: "string" },
      age: { type: "number", minimum: 18 }
    }
  }
})
```

#### $mod:
```sql
db.collection.find({ field: { $mod: [5, 0] } })
```

#### $expr:
```sql
db.collection.find({
  $expr: { $gt: [{ $add: ["$field1", "$field2"] }, 10] }
})
```
#### $text:
```sql
db.collection.find({ $text: { $search: "keyword" } })
```
```sql
db.products.createIndex({name:"text"})
```
