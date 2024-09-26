# Yhteen tauluun kohdistuvien kyselyiden harjoitukset

### Tehtävä 1
SELECT * FROM goal
![img_1.png](img_1.png)

### Tehtävä 2
SELECT name, type FROM airport WHERE iso_country = 'FI';
![img_2.png](img_2.png)

### Tehtävä 3
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name ASC;
![img_3.png](img_3.png)

### Tehtävä 4
SELECT name, type FROM airport WHERE iso_country = 'FI' ORDER BY type ASC, name ASC;
![img_4.png](img_4.png)

### Tehtävä 5
SELECT name FROM country WHERE name LIKE 'F%';
![img_5.png](img_5.png)

### Tehtävä 6
SELECT name FROM country WHERE name LIKE '%F%';
![img_6.png](img_6.png)

### Tehtävä 7
SELECT location FROM game WHERE screen_name = 'Vesa';
![img_7.png](img_7.png)

### Tehtävä 8
SELECT co2_consumed FROM game WHERE screen_name = 'Ilkka';
![img_8.png](img_8.png)

### Tehtävä 9
SELECT DISTINCT co2_budget FROM game;
![img_9.png](img_9.png)


# Where-osan liitosehto harjoitukset

### Tehtävä 1
SELECT country.name AS "country name", airport.name AS "airport name" FROM country JOIN airport ON country.iso_country = airport.iso_country WHERE country.name = 'Iceland';
![img_10.png](img_10.png)

### Tehtävä 2
SELECT name AS "airport name" FROM airport WHERE iso_country = 'FR' AND type = 'large_airport';
![img_11.png](img_11.png)

### Tehtävä 3
SELECT country.name AS country_name, airport.name AS airport_name FROM airport JOIN country ON airport.iso_country = country.iso_country WHERE airport.continent = 'AN';
![img_12.png](img_12.png)

### Tehtävä 4
SELECT elevation_ft FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = 'Heini';
![img_13.png](img_13.png)

### Tehtävä 5
SELECT elevation_ft * 0.3048 AS elevation_m FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = 'Heini';
![img_14.png](img_14.png)

### Tehtävä 6
SELECT airport.name FROM airport JOIN game ON airport.ident = game.location WHERE game.screen_name = 'Ilkka';
![img_15.png](img_15.png)

### Tehtävä 7
SELECT DISTINCT country.name FROM country JOIN airport ON country.iso_country = airport.iso_country JOIN game ON airport.ident = game.location WHERE game.screen_name = 'Ilkka';
![img_16.png](img_16.png)

### Tehtävä 8
SELECT goal.name FROM goal JOIN goal_reached ON goal.id = goal_reached.goal_id JOIN game ON goal_reached.game_id = game.id WHERE game.screen_name = 'Heini';
![img_17.png](img_17.png)

### Tehtävä 9
SELECT DISTINCT airport.name FROM airport JOIN goal_reached ON airport.ident = (SELECT location FROM game WHERE screen_name = 'Ilkka') JOIN goal ON goal_reached.goal_id = goal.id WHERE goal.name = 'clouds';
![img_18.png](img_18.png)

### Tehtävä 10
SELECT DISTINCT country.name FROM country JOIN airport ON country.iso_country = airport.iso_country JOIN goal_reached ON airport.ident = (SELECT location FROM game WHERE screen_name = 'Ilkka') JOIN goal ON goal_reached.goal_id = goal.id WHERE goal.name = 'clouds';
![img_19.png](img_19.png)


# Join harjoitukset

### Tehtävä 1
SELECT country.name AS "country name", airport.name AS "airport name" FROM airport JOIN country ON airport.iso_country = country.iso_country WHERE country.name = 'Finland' AND airport.scheduled_service = 'yes';
![img_20.png](img_20.png)

### Tehtävä 2
SELECT game.screen_name, airport.name FROM game JOIN airport ON game.location = airport.ident;
![img_21.png](img_21.png)

### Tehtävä 3
SELECT game.screen_name, country.name FROM game JOIN airport ON game.location = airport.ident JOIN country ON airport.iso_country = country.iso_country;
![img_22.png](img_22.png)

### Tehtävä 4
SELECT airport.name, game.screen_name FROM airport LEFT JOIN game ON airport.ident = game.location WHERE airport.name LIKE '%Hels%';
![img_23.png](img_23.png)

### Tehtävä 5
SELECT goal.name AS "goal name", game.screen_name FROM goal JOIN goal_reached ON goal.id = goal_reached.goal_id JOIN game ON goal_reached.game_id = game.id;
![img_24.png](img_24.png)


# Sisäkysely harjoitukset

### Tehtävä 1
SELECT country.name FROM country JOIN airport ON country.iso_country = airport.iso_country WHERE airport.name LIKE 'Satsuma%';
![img_25.png](img_25.png)

### Tehtävä 2
SELECT airport.name FROM airport JOIN country ON airport.iso_country = country.iso_country WHERE country.name = 'Monaco';
![img_26.png](img_26.png)

### Tehtävä 3
SELECT game.screen_name FROM game JOIN goal_reached ON game.id = goal_reached.game_id JOIN goal ON goal_reached.goal_id = goal.id WHERE goal.name = 'CLOUDS';
![img_27.png](img_27.png)

### Tehtävä 4
SELECT country.name FROM country WHERE country.iso_country NOT IN (SELECT DISTINCT airport.iso_country FROM airport);
![img_28.png](img_28.png)

### Tehtävä 5
SELECT goal.name FROM goal WHERE goal.id NOT IN (SELECT goal.id FROM goal JOIN goal_reached ON goal.id = goal_reached.goal_id JOIN game ON goal_reached.game_id = game.id WHERE game.screen_name = 'Heini');
![img_29.png](img_29.png)


# Koostetieto kyselyt harjoitukset

### Tehtävä 6
SELECT MAX(elevation_ft) AS max_elevation FROM airport;
![img_30.png](img_30.png)


