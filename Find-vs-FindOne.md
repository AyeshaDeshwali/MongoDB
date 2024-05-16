## 1. find:

#### find method ek cursor return karta hai jo ek query ke matching documents ko represent karta hai.
#### Agar query ke according multiple documents match karte hain, toh find method un documents ko ek cursor ke roop mein return karta hai.
#### Yeh method ek array of documents ko return nahi karta hai. Document ko access karne ke liye cursor ke methods jaise forEach, map, toArray, etc. ka istemal kiya jata hai.
#### Example:

```sql
db.collection.find({ condition: value });
```

## 2. findOne:
#### findOne method ek document return karta hai jo query ke first matching document ko represent karta hai.
#### Agar query ke according multiple documents match karte hain, toh findOne method sirf pehle matching document ko return karta hai.
#### Yeh method directly ek document ko return karta hai, jise aap directly access kar sakte hain.

#### Example:
```sql
db.collection.findOne({ condition: value });
```

### find method ek cursor return karta hai jisme multiple documents hote hain, jabki findOne method sirf pehla matching document return karta hai.



