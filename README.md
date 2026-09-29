# SQL and Python Integration

An educational example of connecting Python to a SQLite database and performing
basic CRUD (create, read, update, delete) operations on sales records.

## Why this project is useful

This small project is designed to make the Python/SQL boundary easy to explore:

- Uses Python's standard-library `sqlite3` module, so there are no third-party
  dependencies.
- Includes a ready-to-use `sales_data.db` SQLite database.
- Includes `sales_data.sql`, a portable SQL dump for recreating the `sales`
  table and sample data.
- Demonstrates parameterized SQL statements for inserting, updating, and
  deleting records.
- Provides a compact starting point for experimenting with database-backed
  Python applications.

## Getting started

### Prerequisites

- Python 3.8 or newer
- SQLite 3 (optional, useful for inspecting the database from the command
  line)

### Run the example

Clone the repository and run the script from the project directory:

```bash
git clone https://github.com/VoidLance/course-files-sql-python-integration.git
cd course-files-sql-python-integration
python3 main.py
```

The script connects to `sales_data.db`, creates a sample sale, prints the
available sales, updates a record, and attempts to delete a record. The sample
calls in `main.py` are intentionally kept in the script so they can be edited
while learning.

> **Note:** Running the script changes the bundled database by inserting and
> updating rows. Make a copy of `sales_data.db` before repeated experiments if
> you want to preserve the original sample data.

### Inspect the database

Use the SQLite CLI to view the schema and records:

```bash
sqlite3 sales_data.db
```

```sql
.schema sales
SELECT * FROM sales;
.quit
```

To recreate a database from the SQL dump, use a separate database file:

```bash
sqlite3 sales_data_copy.db < sales_data.sql
```

## Project structure

| File | Purpose |
| --- | --- |
| `main.py` | Python example containing the SQLite connection and CRUD functions |
| `sales_data.db` | Bundled SQLite database with sample sales data |
| `sales_data.sql` | SQL dump for recreating the sample database |
| `SPLIT_REPO.md` | Notes about the repository's origin |

The `sales` table contains `sale_id`, `product_name`, `quantity`, `sale_date`,
and `amount` columns.

## Help and documentation

This repository is a focused course example and does not currently include
separate API documentation or a test suite. For help:

- Review the SQL statements and function calls in [`main.py`](main.py).
- Consult the
  [Python `sqlite3` documentation](https://docs.python.org/3/library/sqlite3.html).
- Consult the [SQLite documentation](https://www.sqlite.org/docs.html).
- Report reproducible problems or ask questions in the
  [repository issue tracker](https://github.com/VoidLance/course-files-sql-python-integration/issues).

## Contributing

Contributions from learners are welcome. Open an issue first for substantial
changes, then submit a pull request with a clear description of what changed
and how it was checked. Keep examples focused, use the Python standard library
where practical, and avoid committing generated or personal database files.

## Maintainer

Maintained by [VoidLance](https://github.com/VoidLance). Contributions and
feedback are welcome through GitHub issues and pull requests.

## License

No license file is currently included in this repository. If you plan to reuse
the code, please open an issue to discuss licensing.
