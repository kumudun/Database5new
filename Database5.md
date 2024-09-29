# Week 5
## exercise 6 - Aggregate Queries
### Question 1
select max(elevation_ft) from airport;
![screenshot](Screenshot-Q-1.png)

### Question 2
select continent, count(*) from country group by continent;
![screenshot](Screenshot-Q-2.png)

### Question 3
select screen_name, count(*) from game, goal_reached where id = game_id group by screen_name;
![screenshot](Screenshot-Q-3.png)

### Question 4
select screen_name from game where co2_consumed in(select min(co2_consumed) from game );
![screenshot](Screenshot-Q-4.png)

### Question 5
select country.name, count() 
from airport, country 
where airport.iso_country = country.iso_country group by country.iso_country order by count() desc limit 50;

![screenshot](Screenshot-Q-5.png)

### Question 6
select country.name
from airport, country 
where airport.iso_country = country.iso_country group by country.iso_country having count(*) > 1000;
![screenshot](Screenshot-Q-6.png)

### Question 7
select name from airport where elevation_ft in ( select max(elevation_ft) from airport );
![screenshot](Screenshot-Q-7.png)

### Question 8
select name
from country
where iso_country in ( select iso_country from airport where elevation_ft in( select max(elevation_ft) from airport ) );
![screenshot](Screenshot-Q-8.png)

### Question 9
select count(*) from game, goal_reached where id = game_id and screen_name = "Vesa" group by screen_name;
![screenshot](Screenshot-Q-9.png)

### Question 10
select name from airport where latitude_deg in( select min(latitude_deg) from airport );
![screenshot](Screenshot-Q-10.png)