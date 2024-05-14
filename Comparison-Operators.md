## Comparison Operators in MongoDB

#### Find document(s) with age greater than 30

```sql
db.Students.find({ age: { $gt: 30 } })
```
#### Find document(s) where age is less than 5

```sql
db.products.find({ age: { $lt: 5 } })
```

#### Find document(s) with age less than or equal to 30

```sql
db.Students.find({ age: { $lte: 30 } })
```

#### Find document(s) with age greater than or equal to 30

```sql
db.Students.find({ age: { $gte: 18 } })
```
#### Find document(s) with age between 25 and 35 (inclusive)

```sql
db.Students.find({ age: { $gte: 25, $lte: 35 } })
```

#### Find document(s) with age not equal to 40

```sql
db.Students.find({ age: { $ne: 40 } })
```

#### Find document(s) with age equal to 40

```sql
db.Students.find({ age: { $eq: 40 } })
```

#### Find document(s) with name 'John' or 'Alice'

```sql
db.Students.find({ name: { $in: ['John', 'Alice'] } })
```

#### Find document(s) with name not 'John' and not 'Alice'

```sql
db.Students.find({ name: { $nin: ['John', 'Alice'] } })
```

#### Find document(s) with the name 'ayesha' and only retrieve the 'hobbies' field
```sql
db.Students.find({ name: 'ayesha' }, { hobbies: 1, _id: 0 })
```
