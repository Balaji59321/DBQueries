# DBQueries

Exercise 1 — Tasks

1.Find the title of each film :
SELECT title FROM movies;

2.Find the director of each film :
SELECT director FROM movies;

3.Find the title and director of each film
SELECT title,director FROM movies;

4.Find the title and year of each film
SELECT title,year FROM movies;

5.Find all the information about each film
SELECT * FROM movies;

<img width="1165" alt="Screen Shot 2022-04-19 at 11 54 33 PM" src="https://user-images.githubusercontent.com/26063120/164072845-9648ed2f-03a3-4d9e-a7a6-fbd6b714f61e.png">

Exercise 2 — Tasks

1.Find the movie with a row id of 6 
SELECT * FROM movies where id=6;

2.Find the movies released in the years between 2000 and 2010 
SELECT title FROM movies where year between 2000 and 2010;

3.Find the movies not released in the years between 2000 and 2010
SELECT title FROM movies where year not between 2000 and 2010;

4.Find the first 5 Pixar movies and their release year
SELECT title,year FROM movies order by year limit 5;

<img width="1153" alt="Screen Shot 2022-04-20 at 12 07 51 AM" src="https://user-images.githubusercontent.com/26063120/164072891-b387e33d-d86d-41bb-b86b-726edd11a488.png">
