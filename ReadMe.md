# SQL Homework

The Dominion Cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'
```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:
```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions.  Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1. Return ALL the data in the 'movies' table.

SELECT * FROM movies;
psql -d marvel -f marvel.sql  
DROP TABLE
DROP TABLE
CREATE TABLE
CREATE TABLE
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
 id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 17:55
  2 | The Incredible Hulk                 | 2008 | 17:55
  3 | Iron Man 2                          | 2010 | 17:10
  4 | Thor                                | 2011 | 19:30
  5 | Captain America: The First Avenger  | 2011 | 18:50
  6 | Avengers Assemble                   | 2012 | 19:05
  7 | Iron Man 3                          | 2013 | 22:10
  8 | Thor: The Dark World                | 2013 | 23:30
  9 | Batman Begins                       | 2005 | 23:30
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 14:35
 13 | Ant-Man                             | 2015 | 19:15
 14 | Captain America: Civil War          | 2016 | 12:35
 15 | Doctor Strange                      | 2016 | 21:30
(15 rows)

2. Return ONLY the name column from the 'people' table

SELECT name FROM people;
 name        
-------------------
 Faisal Ali
 Samantha Campbell
 Jasmse Cox
 Upul Dissanayaka
 Martin Eguizabel
 Pedro Everett
 Filipe Granha
 Winston Ingram
 Fred
 Reece Jones
 Eugene Kim
 Steven MacDonald
 Fred
 Jamie Martin
 Ciaran McKenna
 Ross Murray
 Victoria Plows
 Finn Porter
 Tom Roddick
 Alan White
 Glen Young
(21 rows)

3. Oops! Someone at CodeClan spelled James' name wrong! Change it to reflect the proper spelling (change 'Jasmse Cox' to 'James Cox').

SELECT id FROM people WHERE name = 'Jasmse Cox';
UPDATE people SET name = 'James Cox' WHERE id = 3;
SELECT name FROM people WHERE id = 3;
 id 
----
  3
(1 row)

UPDATE 1
   name    
-----------
 James Cox
(1 row)

4. Return ONLY your name from the 'people' table.

SELECT name FROM people WHERE name = 'Finn Porter';
 name     
-------------
 Finn Porter
(1 row)


5. The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies WHERE title = 'Batman Begins';
SELECT title FROM movies;
DELETE 1
                title                
-------------------------------------
 Iron Man
 The Incredible Hulk
 Iron Man 2
 Thor
 Captain America: The First Avenger
 Avengers Assemble
 Iron Man 3
 Thor: The Dark World
 Captain America: The Winter Soldier
 Guardians of the Galaxy
 Avengers: Age of Ultron
 Ant-Man
 Captain America: Civil War
 Doctor Strange
(14 rows)


6. Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people (name) VALUES ('Zsolt Podoba-Szalai');
SELECT name FROM people WHERE name = 'Zsolt Podoba-Szalai';
INSERT 0 1
        name         
---------------------
 Zsolt Podoba-Szalai
(1 row)

7. Winston Ingram, has decided to hijack our movie evening, Remove him from the table of people.

DELETE FROM people WHERE name = 'Winston Ingram';
SELECT name FROM people;
DELETE 1
        name         
---------------------
 Faisal Ali
 Samantha Campbell
 Upul Dissanayaka
 Martin Eguizabel
 Pedro Everett
 Filipe Granha
 Fred
 Reece Jones
 Eugene Kim
 Steven MacDonald
 Fred
 Jamie Martin
 Ciaran McKenna
 Ross Murray
 Victoria Plows
 Finn Porter
 Tom Roddick
 Alan White
 Glen Young
 James Cox
 Zsolt Podoba-Szalai
(21 rows)

8. Somehow the list of people includes two people named 'Fred'. Change these entries to the proper names ('Jack Jarvis', 'Victor McDade')

SELECT id FROM people WHERE name = 'Fred';
UPDATE people SET name = 'Jack Jarvis' WHERE id = 9;
UPDATE people SET name = 'Victor McDade' WHERE id = 13;
SELECT name FROM people WHERE id IN(9,13)
id 
----
  9
 13
(2 rows)

UPDATE 1
UPDATE 1
     name      
---------------
 Jack Jarvis
 Victor McDade
(2 rows)


9. The cinema has just heard that they will be holding an exclusive midnight showing of 'Guardians of the Galaxy 2'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Guardians of the Galaxy 2', 2017, '24:00');
SELECT title FROM movies;
INSERT 0 1
                title                
-------------------------------------
 Iron Man
 The Incredible Hulk
 Iron Man 2
 Thor
 Captain America: The First Avenger
 Avengers Assemble
 Iron Man 3
 Thor: The Dark World
 Captain America: The Winter Soldier
 Guardians of the Galaxy
 Avengers: Age of Ultron
 Ant-Man
 Captain America: Civil War
 Doctor Strange
 Guardians of the Galaxy 2
(15 rows)


10. The cinema would also like to make the Guardian movies a back to back feature. Update the 'Guardians of the Galaxy' show time from 12:10 to 21:30

UPDATE movies SET show_time = '21:30' WHERE title = 'Guardians of the Galaxy';
SELECT show_time FROM movies WHERE title = 'Guardians of the Galaxy';
UPDATE 1
 show_time 
-----------
 21:30
(1 row)


## Extension

1. Research how to delete multiple entries from your table in a single command.

DELETE FROM dbname WHERE x IN (a, b)
or
DELETE FROM dbname WHERE x IN (SELECT a FROM dbname WHERE y IN (a, b)) 
