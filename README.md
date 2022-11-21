# SQL-Challenges-and-Projects

This is where I'll be uploading my progress of learning SQL through Challanges and Projects before I complie it into a pretty portfolio
Here you'll see my work in progress
- ST Request: 
- Result: 
###
**Steps:**
###

#
## List of The Top 5 Social Media Sites & Platforms 2022 according to Search Engine Journal by the billion 
- Skills used : CREATE, INSERT SELECT
###
- ST Request: Populate the top 5 social media platforms and have the value of active users(MAU) 
###
**Steps:**
```sql
CREATE TABLE Platforms (id INTEGER PRIMARY KEY, SocialMediaPlatform TEXT, ActiveUserMAU INTEGER);

INSERT INTO Platforms VALUES (1, "Facebook", 2.9);
INSERT INTO Platforms VALUES (2, "Youtube", 2.2);
INSERT INTO Platforms VALUES (3, "WhatsApp", 2.0);
INSERT INTO Platforms VALUES (4, "Instagram", 2.0);
INSERT INTO Platforms VALUES (5, "TikTok", 1);

SELECT* from Platforms;

```
**Result:**

<img src="https://user-images.githubusercontent.com/104226368/202838274-1a53d43a-74fe-4216-b906-1023028422f3.png" width="480" height="350">

#
## Challenge: Box office hits database
- Skills used : CREATE, SELECT, ORDER BY, WHERE
###
- ST Request: Database contains an incomplete list of box office hits and their release year. In this challenge, you're going to get the results back out of the database, retrieves only the movies that were released in the year 2000 or later, not before. Sort the results so that the earlier movies are listed first.

###
**Steps:**
```sql
CREATE TABLE movies (id INTEGER PRIMARY KEY, name TEXT, release_year INTEGER);
INSERT INTO movies VALUES (1, "Avatar", 2009);
INSERT INTO movies VALUES (2, "Titanic", 1997);
INSERT INTO movies VALUES (3, "Star Wars: Episode IV - A New Hope", 1977);
INSERT INTO movies VALUES (4, "Shrek 2", 2004);
INSERT INTO movies VALUES (5, "The Lion King", 1994);
INSERT INTO movies VALUES (6, "Disney's Up", 2009);
 
SELECT* FROM movies;
SELECT* FROM movies WHERE release_year >2000 ORDER BY release_year;
```
**Result:** Populate missing data and organizing the list for movies that were released in the year 2000 ot later and sorting the results
<img src="https://user-images.githubusercontent.com/104226368/202881078-19ea320a-aa35-44b7-be04-2210483b97d8.png" width="480" height="350">



#
## Project: Design a store/organization database (Animal Shelter)
- Skills used : CREATE, SELECT, ORDER BY, WHERE, NULL
###
- ST Request: Create a database that logs the information of animals that are awaiting to be adopted at the shelter

###
**Steps:**
```sql
CREATE TABLE animal_shelter(id INTEGER PRIMARY KEY, species TEXT,breed TEXT,age_by_year INTEGER, adoption_cost INTEGER);
INSERT INTO animal_shelter VALUES (1, "cat", "British Shorthair", 1,200);
INSERT INTO animal_shelter VALUES (2, "dog", "Golden Doodle", NULL,100);
INSERT INTO animal_shelter VALUES (3, "dog", "Beagle", 10,50);
INSERT INTO animal_shelter VALUES (4, "cat", "American Shorthair", 2,200);
INSERT INTO animal_shelter VALUES (5, "dog", "Lab-Pitbull mix", 6,50);
INSERT INTO animal_shelter VALUES (6, "cat", "Ragdoll mix", 1,500);
INSERT INTO animal_shelter VALUES (7, "cat", "Siamese", 3,500);
INSERT INTO animal_shelter VALUES (8, "cat", "Unknown-black", 9,50);
INSERT INTO animal_shelter VALUES (9, "dog", "Corgi mix", 1,500);
INSERT INTO animal_shelter VALUES (10, "dog", "Pug", 4,200);
INSERT INTO animal_shelter VALUES (11, "cat", "Siberian", 3,100);
INSERT INTO animal_shelter VALUES (12, "dog", "Husky", 7,500);
INSERT INTO animal_shelter VALUES (13, "dog", "German Shepherd", 1,200);
INSERT INTO animal_shelter VALUES (14, "dog", "Pitbull", 2,50);
INSERT INTO animal_shelter VALUES (15, "dog", "Bulldog mix", 3,200);
```

###
- ST Request: Which animal has adoption fees under $100, sort by cost from lowest to highest. Also make a table with only adoptable cats, sort by age.

###
**Steps:**
```sql
SELECT* FROM animal_shelter;
/* */
/*Retrieve: Which animal has adoption fees under $100, sort by cost from lowest to highest*/
SELECT* FROM animal_shelter WHERE adoption_cost <=100 ORDER BY adoption_cost;

/*Retrieve: Only adoptable cats, sort by age */
SELECT* FROM animal_shelter WHERE species = "cat" ORDER BY age_by_year;
```


