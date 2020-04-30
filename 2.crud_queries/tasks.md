1. Create a database named `blog`.

<!-- use blog -->

2. Create a collection called 'articles'.

<!-- db.createCollection("articles") -->

3. Insert multiple documents(at least 3) into articles. It should have fields

<!-- db.articles.insert({"title": "Winne the Pooh", "author": "xyz"})

db.articles.insert({"title": "Gravity", "author": "Newton"})

db.articles.insert({"title": "Time Machine", "author": "Einstine"}) -->

4. Find all the articles using `db.COLLECTION_NAME.find()`

<!-- db.articles.find().pretty()
{
	"_id" : ObjectId("5ea6feff2215de07066a55e2"),
	"title" : "Winne the Pooh",
	"author" : "xyz"
}
{
	"_id" : ObjectId("5ea6ff5c2215de07066a55e3"),
	"title" : "Gravity",
	"author" : "Newton"
}
{
	"_id" : ObjectId("5ea6ff5e2215de07066a55e4"),
	"title" : "Time Machine",
	"author" : "Einstine"
}
 -->

5. Find a document using _id field.

<!-- db.articles.find({"_id" : ObjectId("5ea6ff5e2215de07066a55e4")}).pretty() -->

6. Find documents using title and author's name field.

<!-- db.articles.find({"title": "Time Machine", "author": "Einstine"}).pretty() -->

7. Find document using a specific tag.

<!-- db.articles.find({"author": "Newton"}).pretty() -->

8. Update title of a document using its _id field.

<!-- db.articles.update({"_id" : ObjectId("5ea6ff5e2215de07066a55e4")}, {$set : {language: 'english'}}) -->

9. Update a author's name using article's title.

<!-- db.articles.update({"title": "Time Machine"}, {$set: {"author": "New Einstine"}}) -->

10. rename details field to description from articles collection. 

<!-- db.articles.update({}, {$rename: {title : "description"}}) -->

11. Add additional tag in a specific document.

<!-- db.articles.update({"title": "Time Machine"}, {$set : {gender: 'male'}}); -->

12. Update an article's tags using $set and without $set.
  - Write the differences here ?

<!-- db.articles.update({"title": "Time Machine"}, {$set : {gender: 'male'}}); -->


13. Increment an auhtor's age by 5.  

<!-- db.articles.update({"author": "Newton"}, {$inc: {age: 5}}) -->

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

<!-- db.articles.remove({"title" : "Gravity"}) -->

Use sample.js data for below queries.

1. Find all males who play cricket.
<!-- db.users.find({"gender" : "Male"} && {"sports": "cricket"}).count()
//7 -->

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

<!-- db.users.update({"name": "Steve Ortega"}, {$push: {"sports": "golf"}}) -->

3. Find all users who play either 'football' or 'cricket'.

<!-- db.users.find( {sports: "cricket" || "football"} ).count() -->


4. Find all users whose name includes 'ri' in their name.

<!-- db.users.find({name: /\w*ri\w*/ig}) -->