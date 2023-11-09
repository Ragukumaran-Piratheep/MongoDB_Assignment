# MongoDB_Assignment

**01.Create a Database called movies.**
...
test> use Movies
switched to db Movies
...

 **02.Create a collection called moviedetails.**
...
Movies> db.createCollection("Moviedetails")
{ ok: 1 }
...

**03.Create above 5 movie documents into a moviedetails collection.**
...

Movies> db.moviedetails.insertMany([{ "Movie-Title": "Jurassic Park", "Genre/Type": "Adventure" , "Director": "Steven Spielberg" , "Release Year": "1993" },{ "Movie-Title": "Forrest Gump", "Genre/Type": "Drama" , "Director": "Robert Zemeckies" , "Release Year": "1994" }, { "Movie-Title": "Titanic", "Genre/Type": "Romance", "Director": "James Cameron", "Release Year": "1997" }, { "Movie-Title": "The Dark Knight", "Genre/Type": "Action", "Director": "Christopher Nolan", "Release Year": "2008" },{ "Movie-Title": "Avatar", "Genre/Type": "Science Fiction", "Director": "James Cameron", "Release Year":" 2009" }])
...

**04.List all documents created.**
...

Movies> db.moviedetails.find()
[
  {
    _id: ObjectId("654c8b00dc08875c2993aa58"),
    'Movie-Title': 'Jurassic Park',
    'Genre/Type': 'Adventure',
    Director: 'Steven Spielberg',
    'Release Year': 1993
  },
  {
    _id: ObjectId("654c8b00dc08875c2993aa59"),
    'Movie-Title': 'Forrest Gump',
    'Genre/Type': 'Drama',
    Director: 'Robert Zemeckies',
    'Release Year': 1994
  },
  {
    _id: ObjectId("654c8b00dc08875c2993aa5a"),
    'Movie-Title': 'Titanic',
    'Genre/Type': 'Romance',
    Director: 'James Cameron',
    'Release Year': 1997
  },
  {
    _id: ObjectId("654c8b00dc08875c2993aa5b"),
    'Movie-Title': 'The Dark Knight',
    'Genre/Type': 'Action',
    Director: 'Christopher Nolan',
    'Release Year': 2008
  },
  {
    _id: ObjectId("654c8b00dc08875c2993aa5c"),
    'Movie-Title': 'Avatar',
    'Genre/Type': 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': 2009
  }
]
...

**05.List James Cameron’s movies.**
...

Movies> db.moviedetails.find({ "Director": "James Cameron" })
[
  {
    _id: ObjectId("654c8b00dc08875c2993aa5a"),
    'Movie-Title': 'Titanic',
    'Genre/Type': 'Romance',
    Director: 'James Cameron',
    'Release Year': 1997
  },
  {
    _id: ObjectId("654c8b00dc08875c2993aa5c"),
    'Movie-Title': 'Avatar',
    'Genre/Type': 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': 2009
  }
]
...

**06.List  James Cameron’s movies released in 2009.**

...

Movies> db.moviedetails.find({ "Director": "James Cameron","Release Year":2009 })
[
  {
    _id: ObjectId("654c8b00dc08875c2993aa5c"),
    'Movie-Title': 'Avatar',
    'Genre/Type': 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': 2009
  }
]
...

**07.Delete the movie which you don’t like.**
...

db.Movies.remove({"Movie-Title": "Forrest Gump"})
{ acknowledged: true, deletedCount: 0 }

...

**08.Add the movie which is your favourite.**
...

db.moviedetails.find()
[
  {
    _id: ObjectId("654ca1c575a4c6c3f5298594"),
    'Movie-Title': 'Jurassic Park',
    'Genre/Type': 'Adventure',
    Director: 'Steven Spielberg',
    'Release Year': 1993
  },
  {
    _id: ObjectId("654ca1c575a4c6c3f5298595"),
    'Movie-Title': 'Forrest Gump',
    'Genre/Type': 'Drama',
    Director: 'Robert Zemeckies',
    'Release Year': 1994
  },
  {
    _id: ObjectId("654ca1c575a4c6c3f5298596"),
    'Movie-Title': 'Titanic',
    'Genre/Type': 'Romance',
    Director: 'James Cameron',
    'Release Year': 1997
  },
  {
    _id: ObjectId("654ca1c575a4c6c3f5298597"),
    'Movie-Title': 'The Dark Knight',
    'Genre/Type': 'Action',
    Director: 'Christopher Nolan',
    'Release Year': 2008
  },
  {
    _id: ObjectId("654ca1c575a4c6c3f5298598"),
    'Movie-Title': 'Avatar',
    'Genre/Type': 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': 2009
  },
  { _id: ObjectId("654ca4dba71a47ec4d1ae7d5"), 'Movie-Title': 'LEO' }
]

...

**09.List movie Directed  by Christopher Nolan in 1994.**
...

db.moviedetails.find({"Movie-Title":"Christopher Nolan","Release Year":1994})


...

**10.List out the Director’s Name in your document.** 
...

db.moviedetails.distinct("Director")
[
...
  'Christopher Nolan',
  'James Cameron',
  'Robert Zemeckies',
  'Steven Spielberg'
]

...
