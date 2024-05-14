# Logical Query Operators

### $and:

#### Description: Ye operator query clauses ko ek logic AND ke saath jodta hai aur un sabhi dastavizon ko laata hai jo dono clauses ke sharton se milte hain.

#### Exmaple:

```sql
db.Students.find({ $and: [ { age: { $gte: 18 } }, { age: { $lt: 25 } } ] })
```

#### Ye query wahin dastavizon ko laayega jahan umr 18 se lekar 25 tak hai (samaveshi).



### $not:

#### Description: Ye operator ek query vyakhyaa ka prabhav ultaa karta hai aur vyakhyaa ko anuroop dastavizon ko laata hai jo query vyakhyaa se mel nahin khaate hain.

#### Exmaple

```sql
db.Students.find({ age: { $not: { $gte: 18 } } })
```
```sql
db.products.find({$and:[{age :{ $not: {$gt:50}}},{age:{$not:{$lt:10}}}]})
```
#### Ye query wahin dastavizon ko laayega jahan umr 18 se adhik nahin hai.


### $nor:
#### Description: Ye operator query clauses ko ek logical NOR (Not OR) ke saath jodta hai aur un sabhi dastavizon ko laata hai jo dono clauses se mel nahin khaate hain.

#### Example:

```sql
db.Students.find({
  $nor: [
    { age: { $lt: 18 } },
    { age: { $gt: 25 } }
  ]
})
```
#### Ye query un dastavizon ko laayega jinme umr 18 se kam hai ya 25 se adhik hai (dono ko saath me se bachaate hue).

### $or:
#### Description: Ye operator query clauses ko ek logical OR ke saath jodta hai aur un sabhi dastavizon ko laata hai jo kam se kam ek clause ki sharton ko poora karte hain.
#### Example:

```sql
db.Students.find({
  $or: [
    { age: { $lt: 18 } },
    { age: { $gt: 25 } }
  ]
})
```
#### Ye query un dastavizon ko laayega jinme umr 18 se kam hai ya 25 se adhik hai (kam se kam ek shart ko poora karte hue).



## Logical Query Operators in MongoDB

| Name | Description |
|------|-------------|
| $and | Query clauses ko ek logical AND ke saath jodta hai aur vah sabhi documents laata hai jo dono clauses ki sharton ko poora karte hain. |
| $not | Query expression ka ulta prabhav karta hai aur vah documents laata hai jo query expression se mel nahi khaate hain. |
| $nor | Query clauses ko ek logical NOR ke saath jodta hai aur vah sabhi documents laata hai jo dono clauses se mel nahi khaate hain. |
| $or  | Query clauses ko ek logical OR ke saath jodta hai aur vah sabhi documents laata hai jo kisi bhi clause ki sharton ko poora karte hain. |
