# Football Matches - Tasks

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Find all the matches from 2017.

```sql
<!SELECT * FROM matches WHERE season = 2017;


```

2) Find all the matches featuring Barcelona.

```sql
<!SELECT * FROM matches WHERE (hometeam = 'Barcelona') or (awayteam = 'Barcelona');


```

3) What are the names of the Scottish divisions included?

```sql
<!SELECT name FROM divisions WHERE country = 'Scotland';


```

4) Find the value of the `code` for the `Bundesliga` division. Use that code to find out how many matches Freiburg have played in that division. HINT: You will need to query both tables

```sql
<!SELECT code FROM divisions WHERE name = 'Bundesliga';
SELECT count(*) FROM matches WHERE division_code = 'D1' AND (hometeam = 'Freiburg' OR awayteam = 'Freiburg'); 


```

5)  Find the teams which include the word "City" in their name. HINT: Not every team has been entered into the database with their full name, eg. `Norwich City` are listed as `Norwich`. If your query is correct it should return four teams.

```sql
<!SELECT DISTINCT hometeam FROM matches WHERE LOWER(hometeam) LIKE '%city%';


```

6) How many different teams have played in matches recorded in a French division?

```sql
<!SELECT code FROM divisions WHERE country = 'France';
SELECT count(DISTINCT hometeam) FROM matches WHERE (division_code = 'F1') OR (division_code = 'F2');

```

7) Have Huddersfield played Swansea in any of the recorded matches?

```sql
<!SELECT * FROM matches WHERE (LOWER(hometeam) = 'Huddersfield' AND LOWER(awayteam) = 'Swansea') OR (LOWER(hometeam) = 'Swansea' AND LOWER(awayteam) = 'Huddersfield');


### Useful Resources

- [Filtering results](https://www.w3schools.com/sql/sql_where.asp)
- [Ordering results](https://www.w3schools.com/sql/sql_orderby.asp)
- [Grouping results](https://www.w3schools.com/sql/sql_groupby.asp)