# SQL-Challenges-and-Projects

This is where I'll be uploading my progress of learning SQL through Challanges and Projects before I complie it into a pretty portfolio
Here you'll see my work in progress
- Stakeholder (ST)'s: 
- Result: 
###
**Steps:**
###

#
## Challenge: Make a top 5 list (Top 5 Social Media Sites & Platforms 2022 according to Search Engine Journal by the billion)
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
**Result:**

<img src="https://user-images.githubusercontent.com/104226368/202962254-c25ef01d-9c76-495c-932d-21a3fcb36d81.png" width="380" height="450">

###
- ST Request: Which animal has adoption fees under $100, sort by cost from lowest to highest. Also make a seperate table with only adoptable cats, sort by age.

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
**Result:**

<img src="https://user-images.githubusercontent.com/104226368/202962612-1f3c96e5-42d4-47f5-aa18-181e4228944a.png">

# Advance SQL
## Challenge:  Spotify Selected From Top 50 global hits of Winter 2022
- Skills used : SELECT, FROM, WHERE, ORDER BY
###

```sql
CREATE TABLE songs (
    id INTEGER PRIMARY KEY,
    title TEXT,
    artist TEXT,
    album TEXT,
    duration INTEGER,
    released INTEGER);
    
INSERT INTO songs (title, artist, album, duration, released)
    VALUES ("Rich Flex", "Drake_21 Savage", "Her Loss", 150, 2022);
INSERT INTO songs (title, artist, album, duration, released)
    VALUES ("Anti-Hero", "Taylor Swift", "Midnights", 201, 2022);
INSERT INTO songs (title, artist, album, duration, released)
    VALUES ("Unholy", "Sam Smith", "Unholy", 210, 2022);
INSERT INTO songs (title, artist, album, duration, released)
    VALUES ("As It Was", "Harry Styles", "Harry's House", 152, 2022);
INSERT INTO songs (title, artist, album, duration, released)
    VALUES ("Made You Look", "Meghan Trainor", "Takin It Back", 231, 2022);
INSERT INTO songs (title, artist, album, duration, released)
    VALUES ("Glimpse of Us", "Joji", "SMITHEREENS", 237, 2022);
INSERT INTO songs (title, artist, album, duration, released)
    VALUES ("Die For You", "The Weekend", "Starboy", 260, 2016);
INSERT INTO songs (title, artist, album, duration, released)
    VALUES ("All I want for Christmas Is You", "Carly Rae Jepsen", "happy", 241, 1994);    
    SELECT* FROM songs;
```
<img src="https://user-images.githubusercontent.com/104226368/203714321-2d36aa99-6d4c-4224-83b7-ae144dfd5a2a.png">

#
###
- ST Request: We've selected random songs from the top 50 most played song in spotify today. 1) Find out which song came from the album Midnights or released in 2022. 2) Find out which song Joji sang after the year or 2020 and had a duration length of 300 seconds. 3) Pull songs that were released before 2022 and order it by release. 4) Find songs that have a duration no longer than 200 seconds

###
**Steps:**
```sql

SELECT title FROM songs WHERE album = "Midnights" OR released > 2022;
SELECT title FROM songs WHERE artist = "Joji" AND released > 2020 AND duration <300 ORDER BY duration;

SELECT title FROM songs WHERE released <2022 ORDER BY released;

SELECT title FROM songs WHERE duration <200 ORDER BY duration;
```
#
**Result:**

<img src="https://user-images.githubusercontent.com/104226368/203714696-c6987609-0b2f-4a4c-9f7f-eb180bb6400a.png" width="480" height="350">


#
## Challenge: Create a playlist as requested from the client with their favorite songs
- Skills used : SELECT, FROM, WHERE, IN
###
- ST Request: 1) Select the title of all the songs by the artist named 'Queen'. 2) Make a 'Pop' playlist. In preparation, select the name of all of the artists from the 'Pop' genre. 3) Add another query that will select the title of all the songs from the 'Pop' artists. It should use IN on a nested subquery that's based on your previous query.
###
**Steps:**
```sql
CREATE TABLE artists (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    country TEXT,
    genre TEXT);

INSERT INTO artists (name, country, genre)
    VALUES ("Taylor Swift", "US", "Pop");
INSERT INTO artists (name, country, genre)
    VALUES ("Led Zeppelin", "US", "Hard rock");
INSERT INTO artists (name, country, genre)
    VALUES ("ABBA", "Sweden", "Disco");
INSERT INTO artists (name, country, genre)
    VALUES ("Queen", "UK", "Rock");
INSERT INTO artists (name, country, genre)
    VALUES ("Celine Dion", "Canada", "Pop");
INSERT INTO artists (name, country, genre)
    VALUES ("Meatloaf", "US", "Hard rock");
INSERT INTO artists (name, country, genre)
    VALUES ("Garth Brooks", "US", "Country");
INSERT INTO artists (name, country, genre)
    VALUES ("Shania Twain", "Canada", "Country");
INSERT INTO artists (name, country, genre)
    VALUES ("Rihanna", "US", "Pop");
INSERT INTO artists (name, country, genre)
    VALUES ("Guns N' Roses", "US", "Hard rock");
INSERT INTO artists (name, country, genre)
    VALUES ("Gloria Estefan", "US", "Pop");
INSERT INTO artists (name, country, genre)
    VALUES ("Bob Marley", "Jamaica", "Reggae");

CREATE TABLE songs (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    artist TEXT,
    title TEXT);

INSERT INTO songs (artist, title)
    VALUES ("Taylor Swift", "Shake it off");
INSERT INTO songs (artist, title)
    VALUES ("Rihanna", "Stay");
INSERT INTO songs (artist, title)
    VALUES ("Celine Dion", "My heart will go on");
INSERT INTO songs (artist, title)
    VALUES ("Celine Dion", "A new day has come");
INSERT INTO songs (artist, title)
    VALUES ("Shania Twain", "Party for two");
INSERT INTO songs (artist, title)
    VALUES ("Gloria Estefan", "Conga");
INSERT INTO songs (artist, title)
    VALUES ("Led Zeppelin", "Stairway to heaven");
INSERT INTO songs (artist, title)
    VALUES ("ABBA", "Mamma mia");
INSERT INTO songs (artist, title)
    VALUES ("Queen", "Bicycle Race");
INSERT INTO songs (artist, title)
    VALUES ("Queen", "Bohemian Rhapsody");
INSERT INTO songs (artist, title)
    VALUES ("Guns N' Roses", "Don't cry");
    
 
SELECT title FROM songs WHERE artist = "Queen";
SELECT name FROM artists WHERE genre = "Pop";


SELECT title FROM songs 
WHERE artist IN (
SELECT name FROM artists WHERE genre = "Pop" );

```
**Result:**

<img src="https://user-images.githubusercontent.com/104226368/203921669-8f9a5e6e-e723-43b9-9e65-841cfffd29ba.png" width="495" height="353">
<img src="https://user-images.githubusercontent.com/104226368/203921891-c0499189-c550-4f9a-aeeb-b87c0c09dcb2.png" width="490" height="350">


#
## Challenge: Harry Potter Letter Count 
- Skills used : SELECT, SUM, AS, FROM, GROUP BY, HAVING
###
- ST Request: 1) We've created a database of a few popular authors and their books, with word counts for each book. In this first step, select all the authors who have written more than 1 million words, using GROUP BY and HAVING. Your results table should include the 'author' and their total word count as a 'total_words' column. 2)Select all the authors that write more than an average of 150,000 words per book. Your results table should include the 'author' and average words as an 'avg_words' column.

<details><summary> (Click) Book Database</summary>
<p>

```sql
CREATE TABLE books (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    author TEXT,
    title TEXT,
    words INTEGER);
    
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Philosopher's Stone", 79944);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Chamber of Secrets", 85141);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Prisoner of Azkaban", 107253);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Goblet of Fire", 190637);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Order of the Phoenix", 257045);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Half-Blood Prince", 168923);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Deathly Hallows", 197651);

INSERT INTO books (author, title, words)
    VALUES ("Stephenie Meyer", "Twilight", 118501);
INSERT INTO books (author, title, words)
    VALUES ("Stephenie Meyer", "New Moon", 132807);
INSERT INTO books (author, title, words)
    VALUES ("Stephenie Meyer", "Eclipse", 147930);
INSERT INTO books (author, title, words)
    VALUES ("Stephenie Meyer", "Breaking Dawn", 192196);
    
INSERT INTO books (author, title, words)
    VALUES ("J.R.R. Tolkien", "The Hobbit", 95022);
INSERT INTO books (author, title, words)
    VALUES ("J.R.R. Tolkien", "Fellowship of the Ring", 177227);
INSERT INTO books (author, title, words)
    VALUES ("J.R.R. Tolkien", "Two Towers", 143436);
INSERT INTO books (author, title, words)
    VALUES ("J.R.R. Tolkien", "Return of the King", 134462);
```
 
 ###

 </p>
</details>
 
**Steps:**
```sql
SELECT author, SUM(words) AS total_words
FROM "books" GROUP BY "author"
HAVING total_words > 1000000;

SELECT author, AVG(words) AS avg_words
FROM "books" GROUP BY "author"
HAVING avg_words > 150000;

```

 
**Result:**

<img src="https://user-images.githubusercontent.com/104226368/204120985-ef92f712-32e8-4988-8711-4ad6eb975dda.png" width="480" height="350">

#
## Challenge: Analyze Gradebook
- Skills used : SELECT, WHEN, CASE, COUNT, GROUP BY, CASE, END AS, AS
###
- ST Request: 1) We've created a database to track student grades, with their name, number grade, and what percent of activities they've completed. In this first step, select all of the rows, and display the name, number_grade, and percent_completed, which you can compute by multiplying and rounding the fraction_completed column.2) The goal is a table that shows how many students have earned which letter_grade. You can output the letter_grade by using CASE with the number_grade column, outputting 'A' for grades > 90, 'B' for grades > 80, 'C' for grades > 70, and 'F' otherwise. Then you can use COUNT with GROUP BY to show the number of students with each of those grades.

<details><summary> (Click) Grade Database</summary>
<p>

```sql
CREATE TABLE student_grades (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    number_grade INTEGER,
    fraction_completed REAL);
    
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winston", 90, 0.805);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winnefer", 95, 0.901);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winsteen", 85, 0.906);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Wincifer", 66, 0.7054);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winster", 76, 0.5013);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winstonia", 82, 0.9045);
```
 
 ###

 </p>
</details>

**Steps:**
```sql
SELECT  name, number_grade, ROUND (fraction_completed * 100) AS percent_completed FROM student_grades;

SELECT COUNT(*),
    CASE 
        WHEN number_grade > 90 THEN "A"
        WHEN number_grade > 80 THEN "B"
        WHEN number_grade > 70 THEN "C"
        ELSE "F"
    END as "letter_grade"
FROM student_grades
GROUP BY letter_grade;

```
**Result:**

<img src="https://user-images.githubusercontent.com/104226368/204721256-1aa226bb-bee6-44a3-8e00-fed1d116d0b4.png" width="480" height="350">
