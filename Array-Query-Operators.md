# Array-Query-Operators

```
  {
    "name": "hasina",
    "password": "3221",
    "email": "hasina@gmail.com",
    "subjects": [
      "hindi",
      "english",
      "maths",
      "bio",
      "physics"
    ],
    "experience": [
      {
        "company": "Amazon",
        "duration": 4
      },
      {
        "company": "Google",
        "duration": 3
      },
      {
        "company": "Infosys",
        "duration": 10
      }
    ]
  }
```
#### 1. Which students have experience in the 'Amazon' company?

```sql
db.products.find({"experience.company":"Amazon"})
```

#### 2. How many students have worked in Google?

```sql
db.products.find({"experience.company":"Amazon"}).size()
```

#### 3. How many students who have worked in 3 companies
```sql
db.products.aggregate([{ $match: { $expr: { $eq: [{ $size: "$experience" }, 3] } } }, { $count: "totalStudents" }])
```
#### 4. How many students whose hobbies are walking and reading 

```sql
db.students.find({ "hobbies": { "$all": ["walking", "reading"] } }).count()
```

```sql
db.products.find({ "subjects": { "$in": ["hindi", "english"] } }).count()
```
## $all
```
$all Operator:
$all operator ek field ko ek array mein di gayi saari values ke saath match karta hai. Agar document mein wo field
ek array hai aur wo array mein saare specified values maujood hain, tab document match hota hai.
```
#### Example
```sql
db.collection.find({ field: { $all: [value1, value2, ...] } })
```
```
Yeh query saare documents ko retrieve karega jinke 'field' array mein specified values
(value1, value2, etc.) present hain.

```

## $in
```
$in Operator:
$in operator ek field ki value ko specified set of values ke saath match karta hai. Agar document mein wo field
specified values mein se kisi ek ke barabar hai, tab wo document match hota hai.
```

#### Example

```sql
db.collection.find({ field: { $in: [value1, value2, ...] } })
```
```
Yeh query saare documents ko retrieve karega jinke 'field' ki value specified values
(value1, value2, etc.) mein se kisi ek ke barabar hai.
```

#### 4. documents that have at least a product with name apple and quantity greater than 15

```sql
db.products.find({
  $and: [
    { "products.name": "apple" },
    { "products.quantity": { $gt: 15 } }
  ]
})
```
```sql
db.products.find({
 products:{$elemMatch:{quantity:{$gt:15},name:"apple"}}
})

```
