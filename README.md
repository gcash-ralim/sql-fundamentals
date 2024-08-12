# sql-fundamentals

## (Exercise 1) SQL Review: Simple SELECT Queries

Source: https://sqlbolt.com/lesson/filtering_sorting_query_results

#### 1. List all the Canadian cities and their populations
```sql
SELECT City,Country,Population FROM north_american_cities WHERE Country="Canada";
```
#### 2. Order all the cities in the United States by their latitude from north to south
```sql
SELECT * FROM north_american_cities WHERE Country="United States" ORDER BY Latitude DESC;
```
#### 3. List all the cities west of Chicago, ordered from west to east
```sql
SELECT * FROM north_american_cities WHERE Longitude < -87.629798 ORDER BY Longitude ASC;
```
#### 4. List the two largest cities in Mexico (by population)
```sql
SELECT * FROM north_american_cities WHERE Country="Mexico" ORDER BY Population DESC LIMIT 2;
```
#### 5. List the third and fourth largest cities (by population) in the United States and their population
```sql
SELECT City,Country,Population FROM north_american_cities WHERE Country="United States" ORDER BY Population DESC LIMIT 2 OFFSET 2;
```
## (Exercise 2) SQL Lesson 12: Order of execution of a Query

Source: https://sqlbolt.com/lesson/select_queries_order_of_execution

#### 1. Find the number of movies each director has directed 
```sql
SELECT Director, COUNT() FROM movies GROUP BY Director;
```
#### 2. Find the total domestic and international sales that can be attributed to each director
```sql
SELECT DIRECTOR, SUM(Domestic_sales + International_sales) as Sales FROM Movies INNER JOIN Boxoffice ON Movies.Id = Boxoffice.Movie_id GROUP BY Director;
```
## (Exercise 3) sqlpd.com

#### 1. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all records' details.
```sql
SELECT * FROM mailing_list;
```
#### 2. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all records' details.
```sql
SELECT * FROM mailing_list;
```
#### 3. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all entries email addresses, given names and join dates' details.
```sql
SELECT EmailAddress, GivenName, JoinDate FROM mailing_list;
```
#### 4. A hacked site members' details have surface on a darknet forum. Please submit all members names, number of comments and hashed passwords' details.
```sql
SELECT Name, Comments, HashedPassword FROM members;
```
#### 5. An illegal site's servers were seized in a recent operation. Please submit all users number of posts' details. Please make sure there are no duplicates.
```sql
SELECT DISTINCT NumberOfPosts FROM users;
```
#### 6. A hacked site subscribers' details have surfaced on a darknet forum. Please submit all subscribers' details sorted by mailing addresses in ascending order.
```sql
SELECT * FROM subscribers ORDER BY MailingAddress ASC;
```
#### 7. A hacked site members' details have surfaced on a darknet forum. Please submit all members' details sorted by usernames in descending order.
```sql
SELECT * FROM members ORDER BY Username DESC;
```
#### 8. White hat hacker has sent SQLPD exposed subscribers' details of a shady site connected to various persons of interest. Please submit all subscribers number of purchases, hashed passwords and subscribed since dates' details sorted by number of purchases in descending order. Please make sure there are no duplicates.
```sql
SELECT DISTINCT NumberofPurchases, HashedPassword, SubscribedSince FROM subscribers ORDER BY NumberOfPurchases DESC;
```
#### 9. A hacked site subscribers' details sorted by names in ascending order and then by number of purchases in descending order.
```sql
SELECT Name, NumberOfPurchases FROM subscribers ORDER BY Name ASC, NumberOfPurchases DESC;
```
#### 10. An illegal site's servers were seized in a recent operation. Please submmit the top 20 users' details when sorted by access times in ascending order and then by last names in descending order.
```sql
SELECT * FROM users ORDER BY AccessTime ASC, LastName DESC LIMIT 20;
```
#### 11. An illegal site's servers were seized in a recent operation. Please submit the top 20 users access times, first names and number of downloads' details when sorted by number of downloads in descending order and then by first names in ascending order. Please make sure there are no duplicates.
```sql
SELECT DISTINCT AccessTime, FirstName, Downloads FROM users ORDER BY Downloads DESC, FirstName ASC LIMIT 20;
```
