# Intermediate SQL Part 3 : Summarizing data with aggregate functions.

## An aggregate function performs a calculation on several values and returns a single value.

- ```AVG()``` : with numerical data
- ```SUM()``` : with numerical data
- ```MIN()``` : with both numerical and non-numerical fields.
- ```MAX()``` : with both numerical and non-numerical fields.
- ```COUNT()``` : with both numerical and non-numerical fields.


* Sum of film durations

```roomsql
SELECT SUM(duration) AS total_duration
FROM films
```

* Calculate the average duration of all films

```roomsql
SELECT AVG(duration) AS average_duration
FROM films
```

* Find the latest release_year

```roomsql
SELECT MAX(release_year) AS latest_year
FROM films
```

* Find the duration of the shortest film

```roomsql
SELECT MIN(duration) AS shortest_film
FROM films
```

* Calculate the sum of gross from the year 2000 or later

```roomsql
SELECT SUM(gross) AS total_gross
FROM films
WHERE release_year >= 2000
```

* Calculate the average gross of films that start with A

```roomsql
SELECT AVG(gross) AS avg_gross_A
FROM films
WHERE title LIKE 'A%'
```

* Calculate the lowest gross film in 1994

```roomsql
SELECT MIN(gross) AS lowest_gross
FROM films
WHERE release_year IN (1994)
```

* Calculate the highest gross film released between 2000-2012

```roomsql
SELECT MAX(gross) AS highest_gross
FROM films
WHERE release_year BETWEEN 2000 AND 2012
```

* Round the average number of facebook_likes to one decimal place

```roomsql
SELECT ROUND(AVG(facebook_likes), 1) AS avg_facebook_likes
FROM reviews
```

* Calculate the average budget rounded to the thousands

```roomsql
SELECT ROUND(AVG(budget), -3) AS avg_budget_thousands
FROM films
```

* Calculate the percentage of people who are no longer alive

```roomsql
SELECT COUNT(deathdate) * 100.0 /  COUNT(*) AS percentage_dead
FROM people;
```

* Find the number of decades in the films table

```roomsql
SELECT (MAX(release_year) - MIN(release_year)) / 10.0 AS number_of_decades
FROM films;
```

* Round duration_hours to two decimal places

```roomsql
SELECT title, Round(duration / 60.0, 2) AS duration_hours
FROM films;
```

