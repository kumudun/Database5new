# Week 5
## exercise 6 - Aggregate Queries
### Question 1
select max(elevation_ft) from airport;
![screenshot](Screenshot1.png)

### Question 2
select continent,count(*) from country group by continent;
![screenshot](Screenshot2.png)

### Question 3
select screen_name, count(*) from game, goal_reached where id = game_id group by screen_name;
![screenshot](Screenshot3.png)

### Question 4
select screen_name from game where co2_consumed in(select min(co2_consumed) from game );
![screenshot](Screenshot4.png)

### Question 5
select country.name, count() 
from airport, country 
where airport.iso_country = country.iso_country group by country.iso_country order by count() desc limit 50;

![screenshot](Screenshot5.png)

### Question 6
select country.name
from airport, country 
where airport.iso_country = country.iso_country group by country.iso_country having count(*) > 1000;
![screenshot](Screenshot6.png)

### Question 7
select name from airport where elevation_ft in ( select max(elevation_ft) from airport );
![screenshot](Screenshot7.png)

### Question 8
select name
from country
where iso_country in ( select iso_country from airport where elevation_ft in( select max(elevation_ft) from airport ) );
![screenshot](Screenshot8.png)

### Question 9
select count(*) from game, goal_reached where id = game_id and screen_name = "Vesa" group by screen_name;
![screenshot](Screenshot9.png)

### Question 10
select name from airport where latitude_deg in( select min(latitude_deg) from airport );
![screenshot](Screenshot10.png)