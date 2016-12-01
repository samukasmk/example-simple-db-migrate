# Examples of simple-db-migrate uses
---

There are 3 simple steps to use simple-db-migrate

### Step 1. Installing at OS:

```sh
pip install mysql-python simple-db-migrate
```

### Step 2. Define a config file

simple-db-migrate.conf

```python
DATABASE_HOST = "localhost"
DATABASE_USER = "root"
DATABASE_PASSWORD = ""
DATABASE_NAME = "migration_example"
DATABASE_MIGRATIONS_DIR = "./scripts"
DATABASE_VERSION_TABLE  = "simpledbmigrate_version"
```

### Step 3. Create SQL scripts with SQL_UP var for upgrade database and SQL_DOWN to downgrade alterations

- scripts/20161201145318_create_some_tables.migration

```python
SQL_UP = """
  CREATE TABLE aleatory (
    id int(11) NOT NULL auto_increment,
    name varchar(255) default NULL,
    PRIMARY KEY  (id)
  );
"""

SQL_DOWN = """
  DROP TABLE aleatory;
"""
```

- scripts/20161201145400_insert_data.migration

```python
SQL_UP = """
  INSERT INTO aleatory
  VALUES (1, 'xpto');
"""

SQL_DOWN = """
  DELETE FROM aleatory WHERE id = 1;
"""
```

### Extra

More and more information: [At creator repo, HERE!](https://github.com/guilhermechapiewski/simple-db-migrate)

Many thanks to:
- [Guilherme Chapiewski - @guilhermechapiewski](https://github.com/guilhermechapiewski)
- [Wandenberg Peixoto - @wandenberg](https://github.com/wandenberg)
- [Franklin Amorim - @cyberelfo](https://github.com/cyberelfo)
- [Thúlio Costa - @thulio](https://github.com/thulio)
- [Iskren Ivov Chernev - @ichernev](https://github.com/ichernev)
- [Wes Rogers - @wesrog](https://github.com/wesrog)
- [Enrico Batista da Luz - @ricobl](https://github.com/ricobl)
- [Gabriel Falcão - @gabrielfalcao](https://github.com/gabrielfalcao)
- [Andrews Medina - @andrewsmedina](https://github.com/andrewsmedina)
- Silvano Buback
- Vladimir Vitvitskiy
- And many, many people! :D
