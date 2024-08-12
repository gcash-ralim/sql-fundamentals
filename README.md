# sql-fundamentals

## (Exercise 1) SQL Review: Simple SELECT Queries

Source: https://sqlbolt.com/lesson/filtering_sorting_query_results

### 1. List all the Canadian cities and their populations
```sql
SELECT City,Country,Population FROM north_american_cities WHERE Country="Canada";
```
### 2. Order all the cities in the United States by their latitude from north to south
```sql
SELECT * FROM north_american_cities WHERE Country="United States" ORDER BY Latitude DESC;
```
### 3. List all the cities west of Chicago, ordered from west to east
```sql
SELECT * FROM north_american_cities WHERE Longitude < -87.629798 ORDER BY Longitude ASC;
```
### 4. List the two largest cities in Mexico (by population)
```sql
SELECT * FROM north_american_cities WHERE Country="Mexico" ORDER BY Population DESC LIMIT 2;
```
### 5. List the third and fourth largest cities (by population) in the United States and their population
```sql
SELECT City,Country,Population FROM north_american_cities WHERE Country="United States" ORDER BY Population DESC LIMIT 2 OFFSET 2;
```
