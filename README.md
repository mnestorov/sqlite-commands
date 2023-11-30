# SQLite Commands

![Licence](https://img.shields.io/badge/Unlicense-red)

## Overview

A brief overview of SQLite, a cheat sheet for common SQLite commands, as well as best practices for integrating SQLite with Laravel projects.

## Table Operations

- [Create a new table](#create-a-new-table)
- [Delete a table](#delete-a-table)
- [Get details of a table structure](#get-details-of-a-table-structure)
- [Print the SQL CREATE statement for an existing table](#print-the-SQL-CREATE-statement-for-an-existing-table)

## Data Operations

- [Insert new data into a table](#insert-new-data-into-a-table)
- [Select all data from a table](#select-all-data-from-a-table)
- [Select specific columns from a table](#select-specific-columns-from-a-table)
- [Update data in a table](#update-data-in-a-table)
- [Delete data from a table](#delete-data-from-a-table)

## Transaction Control Operations

- [Start a new transaction](#start-a-new-transaction)
- [Save the changes made in the transaction](#save-the-changes-made-in-the-transaction)
- [Roll back the changes if any error occurs inside the transaction](#roll-back-the-changes-if-any-error-occurs-inside-the-transaction)

## Table Operations

### Create a new table

```
CREATE TABLE table_name (column1 datatype, column2 datatype, …);
```

### Delete a table

```
DROP TABLE table_name;
```

### Get details of a table structure

```
PRAGMA table_info(table_name);
```

### Print the SQL CREATE statement for an existing table

```
.schema table_name
```

## Data Operations

### Insert new data into a table

```
INSERT INTO table_name (column1, column2, …) VALUES (value1, value2, …);
```

### Select all data from a table

```
SELECT * FROM table_name;
```

### Select specific columns from a table

```
SELECT column1, column2, … FROM table_name;
```

### Update data in a table

```
UPDATE table_name SET column1 = value1, column2 = value2, … WHERE condition;
```

### Delete data from a table

```
DELETE FROM table_name WHERE condition;
```

## Transaction Control Operations

### Start a new transaction

```
BEGIN TRANSACTION;
```

### Save the changes made in the transaction

```
COMMIT;
```

### Roll back the changes if any error occurs inside the transaction

```
ROLLBACK;
```

## SQLite Documentation Links

**For further reference, you can visit the official SQLite documentation:**

- [SQLite Homepage](https://www.sqlite.org/index.html)
- [SQL Syntax](https://www.sqlite.org/lang.html)
- [SQLite Commands](https://www.sqlite.org/cli.html)
- [SQLite Pragmas](https://www.sqlite.org/pragma.html)
- [SQLite Frequently Asked Questions](https://www.sqlite.org/faq.html)

## Best Practices for SQLite with Laravel

When integrating SQLite with Laravel, you should store your SQLite database file within the database directory of your Laravel project. This is because the database directory is designed to hold all database related files and Laravel is configured to easily access this location.

```
/database
    /sqlite
        - database.sqlite
```

**Be sure to update your `.env` file with the appropriate database configuration:**

```
DB_CONNECTION=sqlite
DB_DATABASE=/absolute/path/to/your/database.sqlite
```

Note: When using version control systems like git, remember to add the SQLite database file to your `.gitignore` file to prevent the database from being tracked. This is important because you typically don't want to expose your database data, especially if it contains sensitive information, to the public or have it be part of your source code.

**Here's what you could add to your `.gitignore`:**

```
/database/sqlite/*.sqlite
```

---

## License

This repository is unlicense[d], so feel free to fork.
