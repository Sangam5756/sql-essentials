### `STATION` Table

| Field  | Type    |
| ------ | ------- |
| ID     | INT     |
| CITY   | VARCHAR |
| STATE  | VARCHAR |
| LAT_N  | FLOAT   |
| LONG_W | FLOAT   |

**Q1 Query a list of CITY and STATE from the STATION table.**

```sql
SELECT CITY, STATE
FROM STATION;
```


**Q2: Query a list of `CITY` names from `STATION` for cities that have an even `ID` number.**

- Print the results in any order
- **Exclude duplicates**

```sql
SELECT DISTINCT CITY
FROM STATION
WHERE MOD(ID, 2) = 0;
```


 **Q3: Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.**

- Total CITY count - Distinct CITY count

```sql
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) AS DIFFERENCE
FROM STATION;
```

 **Q4:Query the two cities in STATION with:The shortest and longest CITY namesAlso return the length of  city name**

```sql
-- City with shortest name
(SELECT CITY, LENGTH(CITY) AS NAME_LENGTH
 FROM STATION
 ORDER BY LENGTH(CITY), CITY
 LIMIT 1)

UNION

-- City with longest name
(SELECT CITY, LENGTH(CITY) AS NAME_LENGTH
 FROM STATION
 ORDER BY LENGTH(CITY) DESC, CITY
 LIMIT 1);
```


**Q5 Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.**

```sql
SELECT DISTINCT CITY 
FROM STATION
WHERE CITY LIKE  "a%"
    OR CITY LIKE  "e%"
    OR CITY LIKE  "i%"
    OR CITY LIKE  "o%"
    OR CITY LIKE  "u%";
            
```

**Q6 Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.**

```sql 
SELECT DISTINCT CITY FROM STATION
WHERE CITY LIKE "%a"
    OR CITY LIKE "%e"
    OR CITY LIKE "%i"
    OR CITY LIKE "%o"
    OR CITY LIKE "%u";

```

**Q7 Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.**

```sql
SELECT DISTINCT CITY FROM STATION
WHERE  
    LEFT(UPPER(CITY),1) IN ("A","E","I","O","U")
    AND 
    RIGHT(UPPER(CITY),1) IN ("A","E","I","O","U");

```

**Q8 Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.**

```sql
SELECT DISTINCT CITY FROM STATION
WHERE LEFT(CITY,1) NOT IN ("A","E","I","O","U");
```

**Q9 Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.**

```sql
SELECT DISTINCT CITY FROM STATION
WHERE RIGHT(CITY,1) NOT IN ("A","E","I","O","U");
```

**Q10 Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.**

```sql
SELECT DISTINCT CITY
FROM STATION
WHERE LEFT(UPPER(CITY),1)  NOT IN ('A', 'E', 'I', 'O', 'U')
OR RIGHT(UPPER(CITY),1)  NOT IN ('A', 'E', 'I', 'O', 'U');
```


**Q11 Query the list of CITY names from STATION that  do not start with vowels and do not end with vowels. Your result cannot contain duplicates.**

```sql
SELECT DISTINCT CITY
FROM STATION
WHERE LEFT(UPPER(CITY),1)  NOT IN ('A', 'E', 'I', 'O', 'U')
AND RIGHT(UPPER(CITY),1)  NOT IN ('A', 'E', 'I', 'O', 'U');
```


