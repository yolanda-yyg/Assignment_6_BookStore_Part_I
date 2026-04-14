# Bookstore Database + Python CLI

**Author:** Yuhong Geng

## Description

A small music-themed bookstore backend built with SQLite and Python. The
database stores music-related book categories (Biographies, Learn to Play,
Music Theory, Scores and Collections) and the books that belong to each
category. A Python command-line interface lets the user browse, search,
add, update, and delete books.

## Files

- `createTables.sql` — creates the `category` and `book` tables
- `insertRows.sql` — inserts the sample categories and books
- `bookstore_cli.py` — Python CLI for CRUD operations
- `bookstore.db` — SQLite database file created from the SQL scripts

## Create the database

If you have the `sqlite3` shell installed:

```bash
sqlite3 bookstore.db < createTables.sql
sqlite3 bookstore.db < insertRows.sql
```

Otherwise you can build it from Python:

```bash
python3 -c "import sqlite3; c=sqlite3.connect('bookstore.db'); \
c.executescript(open('createTables.sql').read()); \
c.executescript(open('insertRows.sql').read()); c.commit(); c.close()"
```

## Run the Python CLI

```bash
python3 bookstore_cli.py
```

## Menu options

1. View all categories
2. View all books
3. View books in a category
4. Search books by title
5. Add a new book
6. Update a book price
7. Delete a book
8. Search books by author (extra feature)
9. Quit

## Notes

- All user input is passed through parameterized queries (`?` placeholders).
- The `image` field stores the filename only; the assets can be reused in
  the Flask web app in the next assignment.
- Foreign keys are enabled with `PRAGMA foreign_keys = ON;`.
