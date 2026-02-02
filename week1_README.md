Microsoft Windows [Version 10.0.22631.6199]
(c) Microsoft Corporation. All rights reserved.

C:\Users\BMSCE>D:

D:\>mkdir db

D:\>mongosh "mongodb+srv://pradeepg.o022lm4.mongodb.net/" --apiVersion 1 --username pradeepgcs24_db_user --password pradeepg@414
Current Mongosh Log ID: 69807362d70805d11c1e2620
Connecting to:          mongodb+srv://<credentials>@pradeepg.o022lm4.mongodb.net/?appName=mongosh+2.5.10
MongoNetworkError: B0420000:error:0A000438:SSL routines:ssl3_read_bytes:tlsv1 alert internal error:C:\data\mci\eb36\tmp\boxednode\mongosh\node-v20.19.6\deps\openssl\openssl\ssl\record\rec_layer_s3.c:1605:SSL alert number 80


D:\>cd db

D:\db>mongosh "mongodb+srv://pradeepg.o022lm4.mongodb.net/" --apiVersion 1 --username pradeepgcs24_db_user --password pradeepg@414

D:\db>mongosh "mongodb+srv://pradeepg.o022lm4.mongodb.net/" --apiVersion 1 --username pradeepgcs24_db_user --password pradeepg@414
Current Mongosh Log ID: 6980737b040fa43c601e2620
Connecting to:          mongodb+srv://<credentials>@pradeepg.o022lm4.mongodb.net/?appName=mongosh+2.5.10
Using MongoDB:          8.0.18 (API Version 1)
Using Mongosh:          2.5.10
mongosh 2.6.0 is available for download: https://www.mongodb.com/try/download/shell

For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/

Atlas atlas-11dtgk-shard-0 [primary] test> show dbs
sample_mflix    4.04 MiB
admin         360.00 KiB
local          49.57 GiB
Atlas atlas-11dtgk-shard-0 [primary] test> mongosh
ReferenceError: mongosh is not defined
Atlas atlas-11dtgk-shard-0 [primary] test> use myDatabase
switched to db myDatabase
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.createCollection("social_media")
{ ok: 1 }
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.users.insertMany([
...   {
...     userId: 1,
...     username: "pradeep_g",
...     name: "Pradeep G",
...     email: "pradeep@gmail.com",
...     followers: 520,
...     following: 180,
...     joinedOn: "2024-06-15"
...   },
...   {
...     userId: 2,
...     username: "anita_raj",
...     name: "Anita Raj",
...     email: "anita@gmail.com",
...     followers: 1200,
...     following: 300,
...     joinedOn: "2023-12-01"
...   },
...   {
...     userId: 3,
...     username: "ravi_kumar",
...     name: "Ravi Kumar",
...     email: "ravi@gmail.com",
...     followers: 850,
...     following: 400,
...     joinedOn: "2024-01-20"
...   }
...   ])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('69807543040fa43c601e2621'),
    '1': ObjectId('69807543040fa43c601e2622'),
    '2': ObjectId('69807543040fa43c601e2623')
  }
}
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.posts.insertMany([
...   {
...     postId: 101,
...     userId: 1,
...     content: "Learning MongoDB is fun! 🚀",
...     likes: 120,
...     comments: 15,
...     tags: ["mongodb", "database", "learning"],
...     createdAt: "2025-01-10"
...   },
...   {
...     postId: 102,
...     userId: 2,
...     content: "Design Thinking helps build better products.",
...     likes: 340,
...     comments: 42,
...     tags: ["design", "ux", "hci"],
...     createdAt: "2025-01-12"
...   },
...   {
...     postId: 103,
...     userId: 3,
...     content: "Flutter + Firebase = ❤️",
...     likes: 210,
...     comments: 28,
...     tags: ["flutter", "firebase", "appdev"],
...     createdAt: "2025-01-15"
...   }
... ])
...
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6980754e040fa43c601e2624'),
    '1': ObjectId('6980754e040fa43c601e2625'),
    '2': ObjectId('6980754e040fa43c601e2626')
  }
}
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.comments.insertMany([
...   {
...     commentId: 201,
...     postId: 101,
...     userId: 2,
...     comment: "Absolutely true!",
...     commentedAt: "2025-01-11"
...   },
...   {
...     commentId: 202,
...     postId: 102,
...     userId: 1,
...     comment: "Very informative post 👍",
...     commentedAt: "2025-01-13"
...   }
... ])
...
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('69807557040fa43c601e2627'),
    '1': ObjectId('69807557040fa43c601e2628')
  }
}
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.posts.find({ userId: 1 })
[
  {
    _id: ObjectId('6980754e040fa43c601e2624'),
    postId: 101,
    userId: 1,
    content: 'Learning MongoDB is fun! 🚀',
    likes: 120,
    comments: 15,
    tags: [ 'mongodb', 'database', 'learning' ],
    createdAt: '2025-01-10'
  }
]
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.posts.find({ likes: { $gt: 200 } })
[
  {
    _id: ObjectId('6980754e040fa43c601e2625'),
    postId: 102,
    userId: 2,
    content: 'Design Thinking helps build better products.',
    likes: 340,
    comments: 42,
    tags: [ 'design', 'ux', 'hci' ],
    createdAt: '2025-01-12'
  },
  {
    _id: ObjectId('6980754e040fa43c601e2626'),
    postId: 103,
    userId: 3,
    content: 'Flutter + Firebase = ❤️',
    likes: 210,
    comments: 28,
    tags: [ 'flutter', 'firebase', 'appdev' ],
    createdAt: '2025-01-15'
  }
]
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.users.find({ followers: { $gt: 500 } })
[
  {
    _id: ObjectId('69807543040fa43c601e2621'),
    userId: 1,
    username: 'pradeep_g',
    name: 'Pradeep G',
    email: 'pradeep@gmail.com',
    followers: 520,
    following: 180,
    joinedOn: '2024-06-15'
  },
  {
    _id: ObjectId('69807543040fa43c601e2622'),
    userId: 2,
    username: 'anita_raj',
    name: 'Anita Raj',
    email: 'anita@gmail.com',
    followers: 1200,
    following: 300,
    joinedOn: '2023-12-01'
  },
  {
    _id: ObjectId('69807543040fa43c601e2623'),
    userId: 3,
    username: 'ravi_kumar',
    name: 'Ravi Kumar',
    email: 'ravi@gmail.com',
    followers: 850,
    following: 400,
    joinedOn: '2024-01-20'
  }
]
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.users.updateOne(
...   { username: "pradeep_g" },
...   { $inc: { followers: 50 } }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.users.updateOne(
...   { username: "ravi_kumar" },
...   { $set: { email: "ravikumar@social.com" } }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.comments.deleteOne({ commentId: 201 })
{ acknowledged: true, deletedCount: 1 }
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> db.posts.aggregate([
...   { $group: { _id: null, avgLikes: { $avg: "$likes" } } }
... ])
...
[ { _id: null, avgLikes: 223.33333333333334 } ]
Atlas atlas-11dtgk-shard-0 [primary] myDatabase> ])# BDA
