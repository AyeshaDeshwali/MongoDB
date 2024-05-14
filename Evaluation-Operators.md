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

#### $where:

```sql
db.collection.find({
  $where: function() {
    return this.height / this.width > 1.5;
  }
})
```
