---
title: Book of Git
---

# SQL Scroll

# 📌 Introduction

## Simple Analogy

- **SQL** = the grammar/language 🗣️
- **DBMS** = the classroom 🏫
- **Database** = the notebook 📓

---

## Core Concepts

- **SQL (Structured Query Language)** → the language used to query and manage data.
- **DBMS (Database Management System)** → the software that stores data and executes SQL commands.
- **Database** → the container that organizes tables and other objects.

---

## 🔥 Popular DBMS

- **MySQL** → Fast, widely used for web apps.
- **PostgreSQL** → Advanced features, strong reliability, great for complex applications.
- **SQLite** → Lightweight, file‑based, perfect for local or embedded use.
- **Oracle Database** → Enterprise‑grade, optimized for large‑scale business systems.

---

## 🔄 ETL Cycle

- **Extract** → Pull data from source (DB, file, API).
- **Transform** → Clean/reshape data (types, formats, rules).
- **Load** → Save into target system (DB, JSON, CSV, warehouse).

👉 Core idea: move data **programmatically** and make it usable.

### Python Examples

### SQL → JSON

```python
import sqlite3, json

# Extract
conn = sqlite3.connect("mydb.sqlite")
rows = conn.execute("SELECT id, name FROM users")

# Transform
data = [{"id": r[0], "name": r[1]} for r in rows]

# Load
with open("users.json", "w") as f:
    json.dump(data, f)
```

### SQL → CSV

```python
import sqlite3, csv

# Extract
conn = sqlite3.connect("mydb.sqlite")
rows = conn.execute("SELECT id, name, age FROM users")

# Load
with open("users.csv", "w", newline="") as f:
    writer = csv.writer(f)
    writer.writerow(["id", "name", "age"])   # header
    writer.writerows(rows)
```

---

## 📌 Notes

- **JSON** → Best for web apps, APIs, flexible data exchange.
- **CSV** → Universal bridge format, readable by Excel, Python, R, and most DBMS.

## ⚙️ Install SQLite

```bass
sudo apt update
sudo apt install sqlite3
sqlite3 --version
```

# Chapter One: **CRUD**

| Category           | Examples                                                            |
| ------------------ | ------------------------------------------------------------------- |
| **Commands**       | `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `CREATE`, `DROP`, `ALTER`   |
| **Clauses**        | `FROM`, `WHERE`, `GROUP`, `ORDER`, `HAVING`, `LIMIT`, `OFFSET`      |
| **Joins**          | `JOIN`, `INNER`, `LEFT`, `RIGHT`, `FULL`, `ON`                      |
| **Constraints**    | `PRIMARY`, `KEY`, `FOREIGN`, `UNIQUE`, `CHECK`, `INDEX`             |
| **Data Types**     | `INT`, `INTEGER`, `CHAR`, `VARCHAR`, `TEXT`, `DATE`, `BOOLEAN`      |
| **Other Keywords** | `TABLE`, `DATABASE`, `VIEW`, `AS`, `IN`, `AND`, `OR`, `NOT`, `NULL` |

## ⚠️ Notes

- **Reserved words differ slightly by DBMS**. For example:
  
  - MySQL uses backticks `` `word` `` to escape.
  
  - PostgreSQL uses double quotes `"word"`.
  
  - SQLite accepts double quotes `"word"` or square brackets `[word]`.

- **Best practice**: Avoid reserved words as identifiers. Use descriptive names like `user_group` instead of `group`.

---

> CREATE – sqlite file

```bash
    sqlite3 mydb.sqlite
```

> CREATE 

```sql
CREATE TABLE material (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    texture TEXT,
    scale INTEGER,
    types TEXT
);

INSERT INTO material (texture, scale, types) VALUES
    ('metal', 1, 'classic'),
    ('wood', 1, 'classic'),
    ('wood2', 1, 'classic');
```

> PREVIEW

```sql
SELECT * FROM material;
```

```sql
SELECT * FROM material LIMIT 5;
```

```sql
.schema material
```

```sql
.mode column
.mode table
.headers on
.mode box
.mode markdown
.mode MODE
.tables
SELECT * FROM material;
```

> UPDATE – Change bpm of a specific track

```sql
UPDATE music
SET bpm = 95
WHERE id = 1;
```

> DELETE – Remove a specific track

```sql
DELETE FROM music
WHERE id = 2;
```

### Chapter Two: ✏️ Edit Table

---

> Add a New Column

```sql
    ALTER TABLE music ADD mood VARCHAR(50);
```

> Rename a Column

```sql
    ALTER TABLE music CHANGE `group` gener VARCHAR(100);
```

> Change Column Type

```sql
    ALTER TABLE music MODIFY bpm FLOAT;
```

> Delete a Column

```sql
    ALTER TABLE music DROP COLUMN mood;
```

> Rename the Table

```sql
    RENAME TABLE music TO sonic_scrolls;
```

> Delete the music table

```sql
    DROP TABLE IF EXISTS music;
```

### Chapter Three: 🔎 Search Examples

---

> Search by group name

```sql
    SELECT * FROM music WHERE `group` = 'Echo Phase';
```

> Search by file path (partial match)

```sql
    SELECT * FROM music WHERE file_path LIKE '%track3%';
```

> Search by BPM range

```sql
    SELECT * FROM music WHERE bpm BETWEEN 90 AND 120;
```

> Search by multiple conditions

```sql
    SELECT * FROM music WHERE bpm > 100 AND `group` = 'Chase Sequence';
```

> Sort results by BPM descending

```sql
    SELECT * FROM music ORDER BY bpm DESC;
```
