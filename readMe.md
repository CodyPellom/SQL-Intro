SQL instructions: 
***
To create a new SQL database using postgres; in 
the terminal: $ brew install postgres

then 

$ brew services start postgres

next, we will create the database itself using the create DB command

terminal type in : createDb <nameOfdatabaseHere>

then

terminal: $ psql <nameOfDataBaseHere>

then youll see this if everything is correct:


$ psql
psql (9.6.1)
Type "help" for help.

<NameOfDataBaseHere> =#

**IN ORDER TO QUIT**  
\q \q \q \q \q \q \q \q

Create:
Use all caps for main commands:
inside of the psql application type

CREATE DATABASE demodb.

then to connect to your created server, 

\c demodb

commands:
list all databases:
\l 

example demodbinput:

CREATE TABLE pokemon (
 number INT UNIQUE PRIMARY KEY,
 name VARCHAR NOT NULL,
 type VARCHAR NOT NULL,
 description VARCHAR
);


then, to list the types of relations
\d

to view the schema for the table :
\d+ pokemon

\d+ tablename

now we can do some cool things.
The way we interact withthe language, capital words here interact with SQL:


SELECT * FROM pokemon;

this will show what rows are avaliable, in order to select a table.

then: 

INSERT INTO pokemon (number, name) VALUES (001, 'bulbasaur', 'grass') INSERT 0 1;


**CRUD**


SELECT * FROM pokemon;
-- nothing!


INSERT INTO pokemon (number, name) VALUES (001, 'Bulbasaur');
-- This won't work! Why?


INSERT INTO pokemon (number, name, type) VALUES (001, 'Bulbasaur', 'Grass');
SELECT * FROM pokemon;

-- INSERT worked! Let's add more
INSERT INTO pokemon (number, name, type) VALUES (002, 'Ivysaur', 'Grass');
INSERT INTO pokemon (number, name, type) VALUES (003, 'Venusaur', 'Grass');
INSERT INTO pokemon (number, name, type) VALUES (004, 'Charmander', 'Fire');
INSERT INTO pokemon (number, name, type) VALUES (005, 'Charmeleon', 'Ghost');
INSERT INTO pokemon (number, name, type) VALUES (006, 'Charizard', 'Fire');
INSERT INTO pokemon (number, name, type) VALUES (007, 'Squitle', 'Water');
INSERT INTO pokemon (number, name, type) VALUES (008, 'Wartortle', 'Water');
INSERT INTO pokemon (number, name, type) VALUES (009, 'Blastoise', 'Water');
INSERT INTO pokemon (number, name, type) VALUES (025, 'Pikachu', 'Electric');

-- READ
SELECT * FROM pokemon;


-- UPDATE
UPDATE pokemon SET type = 'Fire' WHERE number = 5;
-- UPDATE pokemon SET name=...


-- DELETE
DELETE FROM pokemon WHERE name = 'Pikachu';


-- DROP deletes tables and databases
DROP TABLE IF EXISTS pokemon;
DROP DATABASE IF EXISTS demodb;

\q --quit



Schemas:

A schema is a picture of the database. 