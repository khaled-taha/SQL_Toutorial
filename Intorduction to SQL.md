# Introduction to SQL

## Suppose you have a table called books with fields (id, title, author, genre, pub_year)

* Select all records

```roomsql
SELECT * FROM books;
```

* Select titles of books

```roomsql
SELECT title FROM books;
```

### Selecting DISTINCT Records

* Select unique authors from the books table
```roomsql
SELECT DISTINCT author FROM books
```

* Select unique authors and genre combinations from the books table
```roomsql
SELECT DISTINCT author, genre
FROM books;
```
### Aliasing: rename the column

* Alias author so that it becomes unique_author
```roomsql
SELECT DISTINCT author AS unique_author
FROM books;
```

### Views: virtual table that is the result of a saved SQL SELECT statement.

- A benefit of this is that whenever the view is accessed,
- it automatically updates the query results to account for any updates to the underlying database.
- Once a view is created, however, we can query it just as we would a normal table by selecting FROM the view.
- Your code to create the view:

```roomsql
CREATE VIEW library_authors AS
SELECT DISTINCT author AS unique_author
FROM books;
```

- Select all columns from library_authors
```roomsql
SELECT * FROM library_authors
```
-------------------------------------------
### LIMIT

- Select the first 10 genres from books using PostgreSQL
```roomsql
SELECT genre FROM books
LIMIT 10
```

- Select the first 10 genres from books using SQL Server
```roomsql
SELECT genre FROM books
TOP 10
```

