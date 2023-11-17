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
``
**output**
``

**7. Update city=SriLanka to John.**
``
**output**
``

**8. Remove the customer from Tokyo.**
``
**output**
``

**9.  Find customers not from Los Angeles.**
``
**output**
``

**10.Find the customers who are older than age 25.**
``
**output**
``

**11.Retrieve the males who are less than 25.**
``
**output**
``

**12.Update Francis age to 35, if Francis is not available upsert.**
``
**output**
``

**13.Retrieve males who are younger than 30 and older than25.**
``
**output**
``

**14.Find a customer who is lesser than or equal to 23.**
``
**output**
``
