#### Find document(s) with the name 'ayesha'

```sql
db.products.find({ name: 'ayesha' })
```

#### Find document(s) where age is greater than 5

```sql
db.products.find({ age: { $gt: 5 } })
```

#### Find document(s) where age is less than 5

```sql
db.products.find({ age: { $lt: 5 } })
```

#### Find document(s) with the name 'ayesha' and only retrieve the 'hobbies' field

```sql
db.products.find({ name: 'ayesha' }, { hobbies: 1, _id: 0 })
```

