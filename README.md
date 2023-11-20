**1. Create a Database called customers.**
``use customers``

**output**
``switched to db customers``

**2. Create a collection called customerdetails.**
``db.createCollection("customerdetails")``

**output**
``{ ok: 1 }``

**3. Insert all documents into the collection named   customerdetails.**
``db.customerdetails.insertMany([{ "name": "John","age":25,"gender":"Male","city":"New york" },{ "name": "Emily","age":22,"gender":"Male","city":"London" },{ "name": "Daniel","age":28,"gender":"Male","city":"Sydney" },{ "name": "Sophia","age":24,"gender":"Female","city":"Paris" },{ "name": "William ","age":26,"gender":"Male","city":"Chicago" },{ "name": "Olivia","age":23,"gender":"Female","city":"Los Angeles" },{ "name": "Benjamin","age":27,"gender":"Male","city":"Toronto" },{ "name": "Mila","age":29,"gender":"Female","city":"Berlin" },{ "name": "James","age":30,"gender":"Male","city":"Tokyo"}])``

**output**
``{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("655736fdbf54fabdde2bbded"),
    '1': ObjectId("655736fdbf54fabdde2bbdee"),
    '2': ObjectId("655736fdbf54fabdde2bbdef"),
    '3': ObjectId("655736fdbf54fabdde2bbdf0"),
    '4': ObjectId("655736fdbf54fabdde2bbdf1"),
    '5': ObjectId("655736fdbf54fabdde2bbdf2"),
    '6': ObjectId("655736fdbf54fabdde2bbdf3"),
    '7': ObjectId("655736fdbf54fabdde2bbdf4"),
    '8': ObjectId("655736fdbf54fabdde2bbdf5")
  }
}``

**4. Retrieve all documents from the collection and sort the results by the “age” field    in ascending order.**
``db.customerdetails.find().sort({ age: -1 }).pretty()``

**output**
``[
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf5"),
    name: 'James',
    age: 30,
    gender: 'Male',
    city: 'Tokyo'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf4"),
    name: 'Mila',
    age: 29,
    gender: 'Female',
    city: 'Berlin'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdef"),
    name: 'Daniel',
    age: 28,
    gender: 'Male',
    city: 'Sydney'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf3"),
    name: 'Benjamin',
    age: 27,
    gender: 'Male',
    city: 'Toronto'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf1"),
    name: 'William ',
    age: 26,
    gender: 'Male',
    city: 'Chicago'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbded"),
    name: 'John',
    age: 25,
    gender: 'Male',
    city: 'New york'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf0"),
    name: 'Sophia',
    age: 24,
    gender: 'Female',
    city: 'Paris'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf2"),
    name: 'Olivia',
    age: 23,
    gender: 'Female',
    city: 'Los Angeles'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdee"),
    name: 'Emily',
    age: 22,
    gender: 'Male',
    city: 'London'
  }
]``

**5. Count the number of females.**
``db.customerdetails.countDocuments({"gender":"Female"})``

**output**
``3``

**6.Insert one document into the customerdetails collection.**
``db.customerdetails.insertOne({
...   firstName: 'John',
...   lastName: 'Doe',
...   email: 'john.doe@example.com'})``

**output**
``{
  acknowledged: true,
  insertedId: ObjectId("655bce23b4fb611e9f0740bc")
}``

**7. Update city=SriLanka to John.**
``db.customerdetails.updateOne({ city: 'SriLanka' },{ $set: { city: 'John' } } )``

**output**
``{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}``

**8. Remove the customer from Tokyo.**
``db.customerdetails.deleteOne({ city: 'Tokyo' })``

**output**
``{ acknowledged: true, deletedCount: 1 }``

**9.  Find customers not from Los Angeles.**
``db.customerdetails.find({ city: { $ne: 'Los Angeles' } })``

**output**
``[
  {
    _id: ObjectId("655736fdbf54fabdde2bbded"),
    name: 'John',
    age: 25,
    gender: 'Male',
    city: 'New york'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdee"),
    name: 'Emily',
    age: 22,
    gender: 'Male',
    city: 'London'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdef"),
    name: 'Daniel',
    age: 28,
    gender: 'Male',
    city: 'Sydney'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf0"),
    name: 'Sophia',
    age: 24,
    gender: 'Female',
    city: 'Paris'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf1"),
    name: 'William ',
    age: 26,
    gender: 'Male',
    city: 'Chicago'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf3"),
    name: 'Benjamin',
    age: 27,
    gender: 'Male',
    city: 'Toronto'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf4"),
    name: 'Mila',
    age: 29,
    gender: 'Female',
    city: 'Berlin'
  },
  {
    _id: ObjectId("655bce23b4fb611e9f0740bc"),
    firstName: 'John',
    lastName: 'Doe',
    email: 'john.doe@example.com'
  }
]``

**10.Find the customers who are older than age 25.**
``db.customerdetails.find({ age: { $gt: 25 } })``

**output**
``[
  {
    _id: ObjectId("655736fdbf54fabdde2bbdef"),
    name: 'Daniel',
    age: 28,
    gender: 'Male',
    city: 'Sydney'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf1"),
    name: 'William ',
    age: 26,
    gender: 'Male',
    city: 'Chicago'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf3"),
    name: 'Benjamin',
    age: 27,
    gender: 'Male',
    city: 'Toronto'
  },
  {
    _id: ObjectId("655736fdbf54fabdde2bbdf4"),
    name: 'Mila',
    age: 29,
    gender: 'Female',
    city: 'Berlin'
  }
]``

**11.Retrieve the males who are less than 25.**
``db.customerdetails.find({ gender: 'male', age: { $lt: 25 } })``

**output**
``    ``

**12.Update Francis age to 35, if Francis is not available upsert.**
``db.customerdetails.updateOne( { firstName: 'Francis' },   { $set: { age: 35 } },{ upsert: true } )``

**output**
``{
  acknowledged: true,
  insertedId: ObjectId("655bd19bf96477c0402a7ed9"),
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 1
}``

**13.Retrieve males who are younger than 30 and older than25.**
``db.customerdetails.find({ gender: 'male', age: { $gt: 25, $lt: 30 } })``

**output**
`` ``

**14.Find a customer who is lesser than or equal to 23.**
``db.customerdetails.findOne({ age: { $lte: 23 } })``

**output**
``{
  _id: ObjectId("655736fdbf54fabdde2bbdee"),
  name: 'Emily',
  age: 22,
  gender: 'Male',
  city: 'London'
}``

