# MongoDB Practice

Part 1. MongoDB Exercise in mongo shell

## create database
Connect to a running mongo instance, use a database named `mongo_practice`.

use mongo_practice

## Insert Documents

Insert the following documents into a `movies` collection.

```
title : Fight Club
writer : Chuck Palahniuk
year : 1999
actors : [
  Brad Pitt
  Edward Norton
]
```
```
db.movies.insert({title:"Fight Club", writer: "Chuck Palahniuk", year: "1999", actors:["Brad Pitt", "Edward Norton"]})
```
```
title : Pulp Fiction
writer : Quentin Tarantino
year : 1994
actors : [
  John Travolta
  Uma Thurman
]
```
```
 db.movies.insert({title:"Pulp Fiction", writer:"Quentin Tarantino", year:"2009", actors:["John Travolta", "Uma Thurman"]})
```
```
title : Inglorious Basterds
writer : Quentin Tarantino
year : 2009
actors : [
  Brad Pitt
  Diane Kruger
  Eli Roth
]
```
```
db.movies.insert({title:"Inglorious Basterds", writer:"Quentin Tarantino", year:"2009", actors:["Brad Pitt", "Diane Kruger", "Eli Roth"]})
```
```
title : The Hobbit: An Unexpected Journey
writer : J.R.R. Tolkein
year : 2012
franchise : The Hobbit
```
```
db.movies.insert({title:"The Hobbit: An unexpected Journey", writer:"J.R.R. Tolkein", year:"2012",franchise:"The Hobbit"})
```
```
title : The Hobbit: The Desolation of Smaug
writer : J.R.R. Tolkein
year : 2013
franchise : The Hobbit
```
```
db.movies.insert({title:"The Hobbit: The Desolation of Smaug", writer:"J.R.R Tolkien", year:"2013", franchise:"The Hobbit"})
```
```
title : The Hobbit: The Battle of the Five Armies
writer : J.R.R. Tolkein
year : 2012
franchise : The Hobbit
synopsis : Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness.
```
```
db.movies.insert({title:"The Hobbit: The Battle of the Five Armies", writer:"J.R.R Tolkien", year:"2002", franchise:"The Hobbit", synopsis:"Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."})
```
```
title : Pee Wee Herman's Big Adventure
```
```
db.movies.insert({title:"Pee Wee Herman's Big Adventures"})
```
```
title : Avatar
```
 db.movies.insert({title:"Avatar"})


### Insert the following documents into a `posts` collection

```
username : GoodGuyGreg
title : Passes out at party
body : Wakes up early and cleans house
```
```
db.posts.insert({username:"GoodGuyGreg", title:"Passes out at Party", body:"Raises your credit score"})
```
```
username : GoodGuyGreg
title : Steals your identity
body : Raises your credit score
```
```
db.posts.insert({ username:"GoodGuyGreg", title:"Steals your identity", body:"Raises your credit score"})
```

```

username : GoodGuyGreg
title : Reports a bug in your code
body : Sends you a Pull Request
```
```
db.posts.insert({username:"GoodGuyGreg", title:"Reports a bug in your code", body:"Sends you a pull request"})
```

```
username : ScumbagSteve
title : Borrows something
body : Sells it
```
```
db.posts.insert({ username:"ScumbagSteve", title:"Borrows something", body:"Sells it"})
```

```
username : ScumbagSteve
title : Borrows everything
body : The end
```
```
db.posts.insert({ username:"ScumbagSteve", title:"Borrows everything", body:"The end"})
```

```
username : ScumbagSteve
title : Forks your repo on github
body : Sets to private
```
```
db.posts.insert({username:"ScumbagSteve", title:"Forks your repo on github", body:"Sets to private"})
```

### Insert the following documents into a `comments` collection

```
username : GoodGuyGreg
comment : Hope you got a good deal!
post : [post_obj_id]
```
where [post_obj_id] is the ObjectId of the `posts` document: "Borrows something"
```
db.comments.insert({ username:"GoodGuyGreg", comment:"Hope you got a good deal!", post:ObjectId("5ca0b7e96435f98b5901f463")})
```
```
username : GoodGuyGreg
comment : What's mine is yours!
post : [post_obj_id]
```
where [post_obj_id] is the ObjectId of the `posts` document: "Borrows everything"
```
db.comments.insert({username:"GoodGuyGreg", comment:"What's mine is yours!", post:ObjectId("5ca0b9706435f98b5901f46a")})
```
```
username : GoodGuyGreg
comment : Don't violate the licensing agreement!
post : [post_obj_id]
```
where [post_obj_id] is the ObjectId of the `posts` document: "Forks your repo on github
```
db.comments.insert({username:"GoodGuyGreg", comment:"Don't violate the licensing agreement!", post:ObjectId("5ca0b8766435f98b5901f467")})
```

```
username : ScumbagSteve
comment : It still isn't clean
post : [post_obj_id]
```
where [post_obj_id] is the ObjectId of the `posts` document: "Passes out at party"
```
db.comments.insert({username:"ScumbagSteve", comment:"It still isn't clean", post:ObjectId("5ca0b8546435f98b5901f466")})
```
```
username : ScumbagSteve
comment : Denied your PR cause I found a hack
post : [post_obj_id]
```
where [post_obj_id] is the ObjectId of the `posts` document: "Reports a bug in your code"
```
db.comments.insert({username:"ScumbagSteve", comment:"Denied your PR cause I found a hack", post:ObjectId("5ca0b9256435f98b5901f469")})
```

## Query / Find Documents

query the `movies` collection to

1. get all documents

db.movies.find()

![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/1.png)


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/1.1.png)

2. get all documents with `writer` set to "Quentin Tarantino"

db.movies.find({writer:"Quentin Tarantino"})

![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.png)

3. get all documents where `actors` include "Brad Pitt"

db.movies.find({actors:"Brad Pitt"})
![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/3.png)
4. get all documents with `franchise` set to "The Hobbit"

db.movies.find({franchise:"The Hobbit"})


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/4.png)


5. get all movies released in the 90s

db.movies.find({year:{$gt:"1990", $lt:"2000"}})


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/5.png)


6. get all movies released before the year 2000 or after 2010

db.movies.find({$or:[{year:{$gt:"2010"}},{year: {$lt:"2000"}}]})


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/6.png)


## Querying related collections

1. find all users

db.users.find().pretty()


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.1.png)
![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/e16562b5cf04b8e036b177cde76c048f04c85750/Final%20Lab%20Task%206/Files/2.1.1.png)

2. find all posts

db.posts.find().pretty()


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.2.final.png)
![image](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.2.1.png)

3. find all posts that was authored by "GoodGuyGreg"

db.posts.find({username:"GoodGuyGreg"})


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.2.png)


4. find all posts that was authored by "ScumbagSteve"

db.posts.find({username:"ScumbagSteve"})


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.3.png)


5. find all comments
   
db.comments.find().pretty()


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.4.png)


6. find all comments that was authored by "GoodGuyGreg"

db.comments.find({username:"GoodGuyGreg"})


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.5.png)


7. find all comments that was authored by "ScumbagSteve"

db.comments.find({username:"ScumbagSteve"}


![image alt](https://github.com/ReynellMiras24-103/Enterprise-Data-Management/blob/5e05b5802edc7c13d85e46ac49b1cdf71afa8455/Final%20Lab%20Task%206/Files/2.6.png)


8. find all comments belonging to the post "Reports a bug in your code"

db.comments.find({username: "Reports a bug in your code"})


