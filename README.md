# DBQueries

Exercise 1 — Tasks

1.Find the title of each film  
SELECT title FROM movies;

2.Find the director of each film  
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


Exercise 3 — Tasks

1.Find all the Toy Story movies  
SELECT * FROM movies where title like 'Toy%';

2.Find all the movies directed by John Lasseter  
SELECT * FROM movies where director = "John Lasseter";

3.Find all the movies (and director) not directed by John Lasseter   
SELECT * FROM movies where director != "John Lasseter";

4.Find all the WALL-* movies   
SELECT * FROM movies where title like "WALL-%";

<img width="1152" alt="Screen Shot 2022-04-20 at 8 29 20 AM" src="https://user-images.githubusercontent.com/26063120/164141875-f8b77527-ad47-40e1-9907-595d458c8c55.png">


Exercise 4 — Tasks

1.List all directors of Pixar movies (alphabetically), without duplicates  
SELECT distinct director FROM movies order by director asc;

2.List the last four Pixar movies released (ordered from most recent to least)  
SELECT * FROM movies order by year desc limit 4;

3.List the first five Pixar movies sorted alphabetically  
SELECT * FROM movies order by title limit 5;

4.List the next five Pixar movies sorted alphabetically  
SELECT * FROM movies order by title limit 5 offset 5;

<img width="1154" alt="Screen Shot 2022-04-20 at 8 34 20 AM" src="https://user-images.githubusercontent.com/26063120/164142077-596b7409-926a-4e40-a713-13d8923ca2b1.png">


 Review 1 — Tasks 

1.List all the Canadian cities and their populations  


