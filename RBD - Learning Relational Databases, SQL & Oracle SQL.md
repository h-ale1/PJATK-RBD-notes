# What is a database?
A database is a collection of organized data (known as "structured data").

Data within a database is organized into tables consisting of **rows** and **columns** and it is indexed so that it can be *updated*, *expanded*, and *deleted* easily. Scalability is the name of the game.

Databases are used by Database Management Systems (data-keeping  of data within a database... Datadatadatadata), which are in turn used by businesses, organizations and others to help with decision-making, data analysis and storing a lot of information.

# Now, what is a "relational" database?
A relational database is made up of a set of tables (relations) with data that fits into a predefined category. A table contains rows and columns. Rows represent entities while columns represent attributes of the entities. A connection between two tables is called a **relationship**.

Each table is likely to need a **Primary Key** to store unique values. **Foreign Keys** are derived from the Primary Key coming from another table for the purpose of initiating a relationship (or in other words, there's a connection between two tables).

To protect from design flaws of the database, **constraints** are introduced into the mix. **Data types** are also introduced, such as varchar, int, smallint, etc.. in order to differentiate between columns and their purpose.

Relational databases are often constructed with a variation of the Structured Query Language (SQL)

Examples of RDBMS: PostgreSQL, MySQL, MS SQL Server, Oracle DBMS


| Advantages                                            | Disadvantages                                                                         |
| ----------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Effective for transactional data                      | The architecture of the database must be carefully constructed before placing in data |
| Flexible & reduced redundancy                         | Requires significant changes in the future as data structure evolves                  |
| Ease of security, access, backup and recovery of data | Optimization can take a long while                                                    |
| Supports multiple users with multiple different rules |                                                                                       |



# Entities, Attributes and Relationships
**Entity**: A definable object, thing, person, etc.. that is differentiated between from others.
(Examples: Lecturers, students, cashiers)
(Examples 2: Course, job, uni application)

**Attributes**: A property or characteristic of an entity.

**Relationships**: 


## Generic and specific

### Entities
A generic entity describes a shared, general characteristic of an entity.

A specific entity is an individual entity that has unique attributes attached to it. 

### Attributes

A thing about an entity.

A generic attribute describes a generic entity, whereas a specific attribute describes a specific entity. Specific attributes include unique details of an entity that makes it unique/individualized (i.e. Jason, 50kg, 175cm, 19 years old). Generic attributes provide a shared pool of characteristics among many entities (i.e. name, weight, height, age).

| Person        |
| ------------- |
| Name          |  
| Gender        |
| Phone         |
| Email address |

The attributes above are generic so as to be able to add multiple different people, or "specific entities".

 | Customer | 
 | -------- |

| ID  | Name | Phone |
| --- | ---- | ----- |
| 102    | Johnny | 324208686 |



## Database integrity

**Integrity**: Protects our database from potential flaws in logic, incorrect data, etc..

Potential problems with databases may include overloading a table that could be broken down into several tables (e.g. including customers and employees in the same table). Each table that is intended to represent a type of object/person needs to be **atomic** in that case, where tables are split for individual types of objects/people.

In other words, individual tables need to be "one thing".

### Entity integrity

In a nutshell, entity integrity just means that every table needs a primary key. The most common, tried-and-tested primary key used by databases are **ids** with data type int. The primary key can never change and it cannot be left out (or "nullified").

### Referential integrity
If two tables have a connection/relationship, and then one of the tables being referenced by the other is deleted, and some data still remains after deletion, then the database loses integrity. Referential integrity keeps data "integral", aka accurate, secure and valid in a related table, such that you don't accidentally delete related data.


### Domain integrity
Domain integrity ==restricts data type to only one type== within each column in order to prevent the wrong data type from entering into an attribute that is only meant for a specific data type. Wooh word salad.

## Relationships
### One-To-One
Entity <-> Attribute

### One-To-Many
Entity <-> Attributes

### Many-to-Many
Entities <-> Entities

Requires Junction Table/Intermediary Table to achieve this relationship effectively in most DB systems.

## Primary and Foreign keys

## Database Normalization
A more protected database design to ==prevent data redundancy==, contradictory data and protects data integrity

## First normal form
Rule 1: All of your columns need to describe something that is ==atomic== (Something that's in its lowest, smallest, indivisible form).
Rule 2: Each data must occupy one row to prevent data redundancy.

**Example 1:** "Name" attribute is not atomic, since they can be separated into First Name, Middle Name, Maiden Name, Last Name, etc.. First and Last name are atomic since they provide a simple descriptor for the entity (for example, a Person).

## Second normal form (Partial dependencies)
Full dependency: When an attribute depends on an entity.
==Partial dependency==: When an attribute depends on an entity but not necessarily to the other entities in a junction table.

Example 1: Putting author's favorite food attribute in a junction table consisting of author id and book id creates a partial dependency, where the fav food is only relevant to the author entity rather than the book entity.

Rule 1: Be able to tell which tables are related to who what and where.
Rule 2: The only time to put more than two attributes that are not foreign keys of two tables in a junction table is when both tables depend on something in common.

## 3rd normal form (transitivity)
**Transitive dependency:** When an attribute depends on another attribute that depends on the primary attributes/keys, but doesn't depend on the primary attribute directly.



Solution: Create a separate entity for the troublesome attributes.

## Boyce-Codd Normalization Form
Requirements: Entity should be in 3rd normal form (this inherits the 3rd normal form requirements, e.g. requires the entity to have no partial dependency and to be atomic).


# Oracle SQL Hello World
Conventionally, writing SQL keywords such as `SELECT` and other commands is done with uppercase letters.

Prints "Hello World" to console
```plsql
SELECT 'Hello World' FROM DUAL
```

## Data types for attributes
> x is a positive integer, TYPE can be any data type supported by the statements.

1. **NUMBER**: 
2. **VARCHAR2(x TYPE)**: Number of characters relative to type X (e.g. number of characters, bytes, etc..)

## Constraints
Constraint: A rule what data we allow in a column/attribute.

**NOT NULL**: A value that has to be not empty/unexisting
**PRIMARY/FOREIGN KEY**:
**CHECK**: Restricts what data is allowed/disallowed (BETWEEN, etc..)
**UNIQUE**: Data has to be unique/dissimilar to other data
**DEFAULT**: Sets a default value

>[!INFO] Constraint example
>```plsql
CREATE TABLE Users(
user_id NUMBER NOT NULL UNIQUE -- Creates a unique non-nullable userid
);

Since user_id is a good enough candidate for a primary key, since primary keys are non-nullable and have to be unique and since each table/entity requires a primary key, you can declare it to be a primary key simply be typing ```PRIMARY KEY``` in place of the other constraints from the example.

>[!TIP]
>If you need to create a table with the same name but with different attributes and such, or you need to delete a table, you have to "drop" or delete it first.
>```plsql
>DROP TABLE Users;

## Named constraints

Constraints need to be named in order to identify which attribute belongs to which column.
```plsql
CREATE TABLE users(
user_id NUMBER,
username VARCHAR2(50 CHAR) NOT NULL UNIQUE,
CONSTRAINT users_pk PRIMARY KEY (user_id) -- Constraint is named and shown on Oracle SQL Developer. Otherwise, it would show something like "SYS_C00023121"
)
```

## Parent-child relationships

## Referencing columns/entity attributes

The equivalent to this (forget about the wrong cardinality between users and projects for a sec):

![[Pasted image 20220409094242.png]]

Would be this:

```plsql
CREATE TABLE Users(
user_id NUMBER,
username VARCHAR2(500 CHAR) NOT NULL UNIQUE,
first_name VARCHAR2(500 CHAR),
last_name VARCHAR2(500 CHAR),

CONSTRAINT users_pk PRIMARY KEY (user_id)
);

CREATE TABLE Projects(
project_id NUMBER,
project_title VARCHAR2(500 CHAR) NOT NULL,
creator NUMBER NOT NULL,

CONSTRAINT projects_users_fk FOREIGN KEY (creator) REFERENCES Users (user_id),
CONSTRAINT project_pk PRIMARY KEY (project_id)
);
```

Note how in the following line, it reads "Name the constraint 'projects_users_fk', reference the attribute 'user_id' from the Users table and name the referenced variable, which is a foreign key, 'creator'". 
`CONSTRAINT projects_users_fk FOREIGN KEY (creator) REFERENCES Users (user_id),`

## Keywords
**CREATE**: Creates an object (e.g. TABLE, DATABASE)

>[!INFO] Example usage
>```plsql
CREATE TABLE users (
user_id NUMBER,
> CONSTRAINT users_pk PRIMARY KEY (user_id)
);

**DROP**: Deletes an object (e.g a TABLE, DATABASE)
>[!INFO] Example usage
>```plsql
DROP TABLE users 
--Discards the previously created table. Table has to exist first in order to be "dropped".

**ALTER**: Modifies/makes changes to an object (e.g. a TABLE)
>[!INFO] Example usage
>```plsql
>-- Adds a first_name attribute to the users table. Requires preceding ALTER keyword for it to work.
>ALTER TABLE users
>ADD first_name VARCHAR2(500 CHAR);

**UPDATE:** Modifies content of the object's children (e.g. a TABLE's data entries)

>[!INFO] Example usage
>```plsql
>-- Changes all name values within the users table
>INSERT INTO users
>VALUES (1, "James");
>
>INSERT INTO users
>VALUES (1, "Madeline");
>
>UPDATE users
>SET first_name = "DojaCat" 

**INSERT INTO**: Inserts new rows in a table
**SELECT**: Selects data from database
**DELETE**: Deletes rows (entry from the table) from a table

### Conjunction keywords (keywords that follow the main keywords)
**WHERE:**
		- LESS THAN
		- LIKE
		- OR
		- AND
		- BETWEEN
		- IS NULL

## Frequently used statements
SELECT * FROM table_name;
Selects every row and column (entries and attributes) from a table

SELECT COUNT(attribute) FROM table_name;
Counts number of entries in a table.

SELECT AVERAGE(attribute) FROM table_name;
Counts number of entries in a table.

SELECT MIN(attribute), MAX(attribute) FROM table_name;
Returns minimum and maximum values from a table.

SELECT SUM(attribute) FROM table_name;
Returns sum of values from a table.

SELECT *
FROM table_name
JOIN table_name2
	ON table_name2.attribute = table_name.attribute
Returns the combination of two tables (By default, only shows commonly shared values in both tables. Replace JOIN with FULL JOIN to get a union of both tables)
