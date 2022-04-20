# DBQueries
# https://sqlbolt.com - Practise Answers

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
SELECT * FROM north_american_cities where country = "Canada";

2.Order all the cities in the United States by their latitude from north to south 
SELECT * FROM north_american_cities where country = "United States" order by latitude desc;

3.List all the cities west of Chicago, ordered from west to east   
SELECT * FROM north_american_cities where longitude < -87.629798 order by longitude;

4.List the two largest cities in Mexico (by population)   
SELECT * FROM north_american_cities where country = "Mexico" order by population desc limit 2;

5.List the third and fourth largest cities (by population) in the United States and their population    
SELECT * FROM north_american_cities where country = "United States" order by population desc limit 2 offset 2;

<img width="1272" alt="Screen Shot 2022-04-20 at 8 52 19 AM" src="https://user-images.githubusercontent.com/26063120/164145298-658fe9e5-75ff-472d-8524-d77766a1c6f2.png">


Exercise 6 — Tasks

1.Find the domestic and international sales for each movie   
SELECT distinct * FROM movies inner join boxoffice on boxoffice.movie_id = movies.id;

2.Show the sales numbers for each movie that did better internationally rather than domestically   
SELECT distinct * FROM movies inner join boxoffice on boxoffice.movie_id = movies.id where boxoffice.international_sales > domestic_sales;

3.List all the movies by their ratings in descending order  
SELECT distinct * FROM movies inner join boxoffice on boxoffice.movie_id = movies.id order by boxoffice.rating desc;

<img width="1258" alt="Screen Shot 2022-04-20 at 9 05 27 AM" src="https://user-images.githubusercontent.com/26063120/164145364-8f8796dc-1f8c-4554-a26c-33a8da18630a.png">


Exercise 7 — Tasks

1. Find the list of all buildings that have employees   
SELECT building FROM employees left join buildings on employees.building = buildings.building_name group by building;   

2.Find the list of all buildings and their capacity   
Select * from buildings;

3.List all buildings and the distinct employee roles in each building (including empty buildings)   
Select * from buildings left join employees on employees.building = buildings.building_name group by role,building_name

<img width="1268" alt="Screen Shot 2022-04-20 at 10 09 23 AM" src="https://user-images.githubusercontent.com/26063120/164152034-2ee91072-c83d-4653-ad04-f8e8b43270c3.png">


Exercise 8 — Tasks 

1.Find the name and role of all employees who have not been assigned to a building   
SELECT name,role FROM employees where Building is null;

2.Find the names of the buildings that hold no employees 
SELECT building_name FROM buildings left join employees on employees.building = buildings.building_name where employees.building is null;

<img width="1264" alt="Screen Shot 2022-04-20 at 10 32 49 AM" src="https://user-images.githubusercontent.com/26063120/164154841-ad0c7438-1bfb-4a80-8155-c221cd40db53.png">


Exercise 9 — Tasks

1.List all movies and their combined sales in millions of dollars   
SELECT title,(domestic_sales+international_sales)/1000000 as millions FROM movies left join boxoffice on boxoffice.movie_id = movies.id;

2.List all movies and their ratings in percent   
SELECT title,(rating*10) FROM movies left join boxoffice on boxoffice.movie_id = movies.id;

3.List all movies that were released on even number years 
SELECT title FROM movies left join boxoffice on boxoffice.movie_id = movies.id where year %2 =0;

<img width="1252" alt="Screen Shot 2022-04-20 at 10 50 40 AM" src="https://user-images.githubusercontent.com/26063120/164156003-84fb51be-ec37-40e1-9b75-981316c91c3b.png">


Exercise 10 — Tasks

1.Find the longest time that an employee has been at the studio    
SELECT * FROM employees order by years_employed desc limit 1;

2.For each role, find the average number of years employed by employees in that role   
SELECT role,avg(years_employed) FROM employees group by role;

3.Find the total number of employee years worked in each building   
SELECT building,sum(years_employed) FROM employees group by building;

<img width="1259" alt="Screen Shot 2022-04-20 at 10 53 54 AM" src="https://user-images.githubusercontent.com/26063120/164156395-feed3d37-c332-4f76-babf-5444bd383230.png">  


Exercise 11 — Tasks 

1.Find the number of Artists in the studio (without a HAVING clause)    
SELECT count(role) FROM employees where role ="Artist";

2.Find the number of Employees of each role in the studio  
SELECT role,count(role) FROM employees group by role;

3.Find the total number of years employed by all Engineers    
SELECT sum(years_employed) FROM employees where role = "Engineer";

<img width="1263" alt="Screen Shot 2022-04-20 at 10 58 01 AM" src="https://user-images.githubusercontent.com/26063120/164156822-61a75ab6-4f44-4a3c-8690-1ea38d0aac8d.png">


Exercise 12 — Tasks  
 
1.Find the number of movies each director has directed    
SELECT director,count(director) FROM movies left join boxoffice on boxoffice.movie_id = movies.id group by director;

2.Find the total domestic and international sales that can be attributed to each director   
SELECT director,sum(domestic_sales + International_sales) FROM movies left join boxoffice on boxoffice.movie_id = movies.id group by director;

<img width="1274" alt="Screen Shot 2022-04-20 at 11 01 46 AM" src="https://user-images.githubusercontent.com/26063120/164157227-2170c9d2-df63-4274-b41a-69dcf86e73ef.png">


Exercise 13 — Tasks

1.Add the studio's new production, Toy Story 4 to the list of movies (you can use any director)   
insert into movies values (4,"Toy Story 4","Peter",1998,92);

2.Toy Story 4 has been released to critical acclaim! It had a rating of 8.7, and made 340 million domestically and 270 million internationally. Add the record to the BoxOffice table.   
insert into boxoffice values (4,8.7,34000000,27000000);

<img width="1265" alt="Screen Shot 2022-04-20 at 11 05 13 AM" src="https://user-images.githubusercontent.com/26063120/164157601-e5f13ffc-4ae2-490e-a088-eda853c027bc.png">


Exercise 14 — Tasks  
 
1.The director for A Bug's Life is incorrect, it was actually directed by John Lasseter      
update movies set director = "John Lasseter" where id =2;

2.The year that Toy Story 2 was released is incorrect, it was actually released in 1999    
update movies set year = "1999" where id =3;

3.Both the title and director for Toy Story 8 is incorrect! The title should be "Toy Story 3" and it was directed by Lee Unkrich     
update movies set director = "Lee Unkrich",title = "Toy Story 3" where id =11;

<img width="1263" alt="Screen Shot 2022-04-20 at 11 09 30 AM" src="https://user-images.githubusercontent.com/26063120/164158156-7b049fd7-be2e-4e77-9939-104fcb50ab9a.png">


Exercise 15 — Tasks

1.This database is getting too big, lets remove all movies that were released before 2005.       
delete from movies where year < 2005;

2.Andrew Stanton has also left the studio, so please remove all movies directed by him.       
delete from movies where director = "Andrew Stanton";

<img width="1259" alt="Screen Shot 2022-04-20 at 11 11 08 AM" src="https://user-images.githubusercontent.com/26063120/164158385-bd80359e-1819-4dee-9024-bff0a56f2b5b.png">


Exercise 16 — Tasks

1.Create a new table named Database with the following columns:

– Name A string (text) describing the name of the database
– Version A number (floating point) of the latest version of this database
– Download_count An integer count of the number of times this database was downloaded
This table has no constraints.     
create table Database (Name varchar(255),Version float,Download_count INT)

<img width="1251" alt="Screen Shot 2022-04-20 at 11 13 48 AM" src="https://user-images.githubusercontent.com/26063120/164158766-a77d70e7-ac81-4b7d-ac5a-023b51a8af8d.png">


Exercise 17 — Tasks

1.Add a column named Aspect_ratio with a FLOAT data type to store the aspect-ratio each movie was released in.       
alter table movies add column Aspect_ratio float; 

2.Add another column named Language with a TEXT data type to store the language that the movie was released in. Ensure that the default for this language is English.      
alter table movies add column Language varchar(255) Default "English";

<img width="1259" alt="Screen Shot 2022-04-20 at 11 17 42 AM" src="https://user-images.githubusercontent.com/26063120/164159155-b4ca5400-a7aa-4e03-9ca4-f65cecb32308.png">


Exercise 18 — Tasks

1.We've sadly reached the end of our lessons, lets clean up by removing the Movies table      
drop table movies;

2.And drop the BoxOffice table as well      
drop table boxoffice;


<img width="1262" alt="Screen Shot 2022-04-20 at 11 18 49 AM" src="https://user-images.githubusercontent.com/26063120/164159332-294c7559-1bfe-489d-9d46-ecc009b2bd36.png">





