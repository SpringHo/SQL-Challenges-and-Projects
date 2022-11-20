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
- Result: This populates the top 5 Social Media Sites & Platforms by Active Users (MAU) by the billions
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
<img src="https://user-images.githubusercontent.com/104226368/202838274-1a53d43a-74fe-4216-b906-1023028422f3.png" width="480" height="350">

#
## Challenge: Box office hits database
- Skills used : CREATE, SELECT, ORDER BY, WHERE
###
- ST Request: 
- Result: 
- Steps:
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
<img src="https://user-images.githubusercontent.com/104226368/202881078-19ea320a-aa35-44b7-be04-2210483b97d8.png" width="480" height="350">
