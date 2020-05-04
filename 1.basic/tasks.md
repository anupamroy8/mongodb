#### write commands for following mongodb opertaions

1. create a database named `sports`
// use sports


2. list all databases present in local mongod server.
// 
> show dbs
admin   0.000GB
config  0.000GB
local   0.000GB
test    0.000GB
//

3. create 3 collections named `cricket`, `football`, `TT` in sports database.

//
> db.createCollection("cricket")
{ "ok" : 1 }
> db.createCollection("football")
{ "ok" : 1 }
> db.createCollection("TT")
{ "ok" : 1 }
//

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.

//
{
	"_id" : ObjectId("5ea6de71bdbd74486538e655"),
	"name" : "Anupam",
	"age" : 22,
	"email" : "aroy8@gmail.com",
	"state" : "WB",
	"auction_price" : 100
}
{
	"_id" : ObjectId("5ea6dea9bdbd74486538e656"),
	"name" : "Rahul",
	"age" : 26,
	"email" : "rahul@gmail.com",
	"state" : "HP",
	"auction_price" : 120
}
{
	"_id" : ObjectId("5ea6dec8bdbd74486538e657"),
	"name" : "Johny",
	"age" : 23,
	"email" : "john@gmail.com",
	"state" : "AP",
	"auction_price" : 120
}
//
5. list all collections in sports database.

//
> show collections
TT
cricket
football
//

6. rename `TT` collection to `tennis`.

//> db.TT.renameCollection("tennis")

7. create a capped collection called `khokho` which should have max 3 documents.

> db.createCollection("khokho", {capped: true, size: 64*1024,  max: 3})


  Try inserting more than 3 and output the result here ?

There was no error just first entire was delete.(FIFO)
//
> db.khokho.find().pretty()
{
	"_id" : ObjectId("5ea6e68ab8eb9fc5f40e1be7"),
	"name" : "Kholi",
	"age" : 22,
	"email" : "Kholi@gmail.com",
	"state" : "HP",
	"auction_price" : 13141
}
{
	"_id" : ObjectId("5ea6e6a2b8eb9fc5f40e1be8"),
	"name" : "Pant",
	"age" : 22,
	"email" : "pantt@gmail.com",
	"state" : "UK",
	"auction_price" : 4343
}
{
	"_id" : ObjectId("5ea6e6dcb8eb9fc5f40e1be9"),
	"name" : "Virat",
	"age" : 22,
	"email" : "virat@gmail.com",
	"state" : "Delhi",
	"auction_price" : 111
}
//

8. check whether a collection is capped or not?

//
> db.khokho.stats()["capped"]
true
//

9. remove all documents from `football` collection.

//db.football.remove({})

10. delete cricket collection completely.

//db.football.drop()

11. rename database sports to games
//
db.copyDatabase("sports","games","localhost")
use sports
db.dropDatabase();
//
12. delete sports database. 
//
db.dropDatabase();