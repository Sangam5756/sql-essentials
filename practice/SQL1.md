### `CITY` Table

| Field       | Type    |
| ----------- | ------- |
| ID          | INT     |
| NAME        | VARCHAR |
| COUNTRYCODE | VARCHAR |
| DISTRICT    | VARCHAR |
| POPULATION  | INT     |

**Q1 Query all columns (attributes) for every row in the CITY table.**

```sql
SELECT * FROM CITY;
```

**Q2 Query all columns for a city in CITY with the ID 1661.**

```sql
SELECT * FROM CITY
WHERE ID = 1661;
```

**Q3 Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.**

```sql
SELECT * FROM CITY
WHERE COUNTRYCODE = 'JPN';
```

**Q4 Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.**

```sql
SELECT * FROM CITY
WHERE COUNTRYCODE ='USA' AND POPULATION > 100000;
```

**Q5 Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.**

```sql
SELECT NAME FROM CITY
WHERE POPULATION > 120000 AND COUNTRYCODE ='USA';
```

**Q6 Query the names of all the Japanese cities (`COUNTRYCODE = 'JPN'`) from the `CITY` table.**

```sql
SELECT NAME
FROM CITY
WHERE COUNTRYCODE = 'JPN';
```
