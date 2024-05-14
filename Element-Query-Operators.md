# Element-Query-Operators

#### In database's 'product' collection, does a product have a 'password' field and is its data type a number? 
```sql 
db.products.find({password:{$exists:true,$type:"number"}})
```
