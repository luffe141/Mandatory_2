# Learning Goals - Eksam Preparation
**Name:**[Jonathan Svarer]
**Date:**[04-05-26]


# Week 1: 27th january

### Can navigate the terminal

```bash
ls                  
cd myFolder
pwd
whoami 
```
I can do it!

### Can create, delete files / folders
```bash
mkdir test
touch file.txt
cp file.txt copy.txt
mv copy.txt moved.txt
rm file.txt
nano moved.txt
```
I can do it!

### Can use the follewinf basic terminal commands

```bash
cat file.txt
wc file.txt
sort file.txt
uniq file.txt
```
I can do it!

### Can create a new Github repository
- Create repo on Github
- Clone locally

I can do it!

### Can perfom basic Git operations
```bash
git clone <url>
git add .
git commit -m "message"
git push
gut pull
```
I can do it!

# Week 2: 3th February

### Can list the main hardware components of a computer, their functions and the Von Neumann architecture
- CPU (processing)
- Ram (tempoary memory)
- storage (permanent)
- input/output devices
- Shared memory for instruction and data

I can do it!

### Can explain how computers work, starting from hardware all the way to software.
- Hardware = physical parts (CPU, RAM, storage)
- Software = programs that tell hardware what to do
- The CPU processes instructions
- Data is stored and used in RAM and storage
- Everything runs on binary (0s and 1s)

I can do it!

### Can talk about processes in operating systems.
- A process is a running program
- The operating system manages processes
- Each process has its own memory and resources
- The CPU switches between processes (multitasking)
- Processes can start, run, wait, and stop

I can do it!

### Can talk about different number representations such as: Binary, Hexadecimal and Decimal

- Decimal (Base 10) – uses digits 0–9 (what we normally use)
- Binary (Base 2) – uses only 0 and 1 (used by computers)
- Hexadecimal (Base 16) – uses 0–9 and A–F (compact way to represent binary)

### Example
- Decimal: 10  
- Binary: 1010  
- Hexadecimal: A 

I can do it!

### Can bring up real-world use cases for different number representations.

- Decimal (Base 10)
  - Used in everyday life (money, measurements, counting)

- Binary (Base 2)
  - Used by computers internally (data, logic, memory)
  - Example: storing files, processing instructions

- Hexadecimal (Base 16)
  - Used in programming and design
  - Example: color codes in web design (#FF5733)
  - Memory addresses and debugging

I can do it!

### Can explain different charsets like ASCII and Unicode and how they differ.
- ASCII
  - Uses 7 bits (128 characters)
  - Includes letters, numbers, and basic symbols
  - Limited (mostly English characters)

- Unicode
  - Supports thousands of characters from all languages
  - Includes emojis and special symbols
  - Common encoding: UTF-8

### Difference
- ASCII is small and limited
- Unicode is large and universal


# Week 3: 10th February

### Knows about different types of databases and their use cases
- Relational Databases (SQL)
  - Structured data in tables
  - Example: MySQL, PostgreSQL
  - Use case: banking systems, web apps

- NoSQL Databases
  - Flexible, non-tabular data
  - Example: MongoDB, Firebase
  - Use case: real-time apps, large-scale data

- Key-Value Databases
  - Simple data as key-value pairs
  - Example: Redis
  - Use case: caching, sessions

- Graph Databases
  - Data as nodes and relationships
  - Example: Neo4j
  - Use case: social networks, recommendations

I can do it!

### Can setup a new MySQL database and connect to it.

- Install and start MySQL
- Create a new database
- Create a user and password
- Give the user permissions
- Connect to the database from an app or terminal

### Example
```sql
CREATE DATABASE my_database;
CREATE USER 'my_user'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON my_database.* TO 'my_user'@'localhost';
```
I can do it!

### Can create DDL statements to create tables.

- DDL (Data Definition Language) is used to define database structure
- Common commands: CREATE, ALTER, DROP

### Example
```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
I can do it!

### Can create DML (SELECT, INSERT) statements.
- DML (Data Manipulation Language) is used to work with data
- Common commands: SELECT, INSERT, UPDATE, DELETE

### SELECT Example
```sql
SELECT * FROM users;
```

I can do it!

### Can use WHERE clause to filter results.
- The WHERE clause is used to filter results in SQL queries
- It allows you to select only the data that meets certain conditions

### Example
```sql
SELECT * FROM users
WHERE name = 'John Doe';
```
I can do it!


# Week 3: 24th February

### Can define Primary Keys

**Example:**
```sql
CREATE TABLE users (
  id INT PRIMARY KEY,
  name VARCHAR(100)
);
```
I can do it!

### Understands how Foreign Keys work.

A foreign key is a column in one table that refers to the primary key in another table.

It is used to create relationships between tables and ensures that the data is valid (referential integrity).

Example:
A user_id in an orders table must exist in the users table.

### In SELECT statements, can use (with moderate help)
- LIMIT – restrict number of results
- ORDER BY – sort results
- GROUP BY – group rows with same values
- Aggregate functions – COUNT, SUM, AVG, MIN, MAX
- LIKE – pattern matching with wildcards (% and _)
- JOIN – combine data from multiple tables

### Examples

```sql
-- LIMIT & ORDER BY
SELECT * FROM users
ORDER BY created_at DESC
LIMIT 5;

-- GROUP BY with COUNT
SELECT country, COUNT(*) 
FROM users
GROUP BY country;

-- Aggregate functions
SELECT AVG(age), MAX(age) 
FROM users;

-- LIKE with wildcard
SELECT * FROM users
WHERE email LIKE '%@gmail.com';

-- JOIN example
SELECT users.name, orders.total
FROM users
JOIN orders ON users.id = orders.user_id;
```

I can do it!

### Can create inner, left and right joins after looking up the syntax.

- INNER JOIN – returns only matching rows from both tables
- LEFT JOIN – returns all rows from left table + matching rows from right
- RIGHT JOIN – returns all rows from right table + matching rows from left

```sql
-- INNER JOIN
SELECT users.name, orders.total
FROM users
INNER JOIN orders ON users.id = orders.user_id;

-- LEFT JOIN
SELECT users.name, orders.total
FROM users
LEFT JOIN orders ON users.id = orders.user_id;

-- RIGHT JOIN
SELECT users.name, orders.total
FROM users
RIGHT JOIN orders ON users.id = orders.user_id;
```
I can do it!

### Can create DDL statements to create tables with constraints: PRIMARY KEY, AUTO_INCREMENT, FOREIGN KEY, UNIQUE, NOT NULL.

- PRIMARY KEY – uniquely identifies each row
- AUTO_INCREMENT – automatically generates IDs
- FOREIGN KEY – links tables together
- UNIQUE – ensures all values are different
- NOT NULL – value is required

### Example
```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  email VARCHAR(100) UNIQUE NOT NULL
);

CREATE TABLE orders (
  id INT AUTO_INCREMENT PRIMARY KEY,
  user_id INT NOT NULL,
  total DECIMAL(10,2) NOT NULL,
  FOREIGN KEY (user_id) REFERENCES users(id)
);
```
I can do it!

### Can create DML (UPDATE, DELETE) statements.
- UPDATE – modify existing data
- DELETE – remove data from a table

### UPDATE Example
```sql
UPDATE users
SET email = 'newemail@example.com'
WHERE id = 1;
```
I can do it!

### Can create a pull request.

- Push your changes to a branch
- Click "Compare & pull request"
- Add a title and description
- Submit the pull request for review

I can do it!

# Week 4: 3rd March

### Understands different Git workflows such as GitHub Flow.

- A workflow is how developers use Git to collaborate

### GitHub Flow
- Create a new branch from `main`
- Make changes and commit
- Push branch to :contentReference[oaicite:0]{index=0}
- Open a pull request
- Review and discuss changes
- Merge into `main`

### Why use it?
- Simple and fast
- Good for continuous deployment
- Keeps `main` stable

### Can solve a merge conflict.

- A merge conflict happens when Git can't automatically combine changes

### Steps to resolve
- Open the conflicted file
- Look for conflict markers:
  ```text
  <<<<<<< HEAD
  your changes
  =======
  incoming changes
  >>>>>>> branch-name

I can do it!

### Can write YAML.
- YAML = "YAML Ain’t Markup Language"
- Used for configuration files
- Uses indentation (spaces, not tabs)

### Example
```yaml
name: MyApp
version: 1.0

database:
  host: localhost
  port: 3306
  user: root
  password: secret

features:
  - login
  - signup
  - dashboard
```

I can do it!

### Understands what GitHub Actions are and can breakdown workflows into runners, jobs, and steps.

- GitHub Actions automate tasks like testing, building, and deploying code

### Key Concepts

- **Workflow**
  - A YAML file that defines automation
  - Stored in `.github/workflows/`

- **Runner**
  - A machine that runs the workflow (e.g. Ubuntu server)

- **Job**
  - A set of steps that run on the same runner

- **Step**
  - Individual tasks within a job (commands or actions)

### Example
```yaml
name: CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Run script
        run: echo "Hello World"
```

### Can give use cases for GitHub Actions.

- Continuous Integration (CI)
  - Automatically run tests when code is pushed

- Continuous Deployment (CD)
  - Automatically deploy apps after successful builds

- Code Quality Checks
  - Run linters and formatters

- Automation
  - Auto-label issues or pull requests
  - Send notifications

- Scheduled Tasks
  - Run jobs at specific times (e.g. backups)

I can do it!

# Week 5: 10rd March

### Understands different cloud service models: IaaS, PaaS, SaaS.

- IaaS (Infrastructure as a Service)
  - Provides virtual servers, storage, networking
  - You manage OS and applications
  - Example: AWS EC2

- PaaS (Platform as a Service)
  - Provides platform to build and deploy apps
  - Provider manages infrastructure and OS
  - Example: Heroku

- SaaS (Software as a Service)
  - Ready-to-use software over the internet
  - Provider manages everything
  - Example: Google Docs

### Difference
- IaaS → most control
- PaaS → balance
- SaaS → least control, easiest to use


### Can deploy a web application to Azure App Service.
- Create an account on Azure
- Create an **App Service**
- Choose runtime (Node.js, .NET, etc.)
- Connect your code (GitHub or local)
- Configure environment settings
- Deploy the app
- Access it via the provided URL

### Example (GitHub Deployment)
- Push code to Github
- Link repository in Azure App Service
- Enable automatic deployment

I can do it!

### Understands the flow from pushing, GitHub Actions running, building the project and deployment to Azure.

- Push code to Github
- A GitHub Actions workflow is triggered
- The runner starts and executes jobs
- Steps run:
  - Install dependencies
  - Build the project
  - Run tests (optional)
- If successful, deploy to Azure App Service
- The app is updated and live

### Summary
Code push → GitHub Actions → Build & Test → Deploy → Live app

# Week 6: 17th March

### Adding a database to a Spring Project.

- Add database dependency in `pom.xml`
- Configure database connection in `application.properties`
- Create an entity/model class
- Create a repository interface
- Use the repository to save, update, delete, and fetch data

### Example `application.properties`
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/my_database
spring.datasource.username=root
spring.datasource.password=password
spring.jpa.hibernate.ddl-auto=update
```

### Setting up a database in Azure.

- Go to Azure Portal
- Create a new database (e.g. Azure SQL Database)
- Choose server, region, and pricing tier
- Set admin username and password
- Configure firewall rules (allow your IP)
- Connect using a connection string

### Example Connection String
```text
jdbc:sqlserver://your-server.database.windows.net:1433;
database=my_database;
user=your_user@your-server;
password=your_password;
encrypt=true;
```

### Can set up a database in Azure and connect it to an Azure App Service project with a guide.

- Create a database in Azure (Azure SQL or MySQL)
- Create a database server with username and password
- Allow Azure services/firewall access
- Copy the database connection string
- Open your Azure App Service
- Go to Configuration -> Application settings
- Add the connection string or environment variables
- Update the app to use the Azure database
- Restart the App Service
- Test that the app can read/write data

### Example Spring Boot Properties
```properties
spring.datasource.url=jdbc:mysql://your-server.mysql.database.azure.com:3306/your_database
spring.datasource.username=your_user
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
```
I can do it!

# Week 7: 24th March


### Is able to go through scenarios that can cause concurrency problems in databases.

- Concurrency issues happen when multiple transactions access the same data at the same time

### Common Scenarios

- Dirty Read
  - A transaction reads data that has not been committed yet

- Lost Update
  - Two transactions update the same data, and one overwrites the other

- Non-Repeatable Read
  - A transaction reads the same row twice and gets different results

- Phantom Read
  - A query returns different rows when run multiple times due to inserts/deletes

### Example
```text
Transaction A reads balance = 100
Transaction B updates balance to 50
Transaction A reads again -> now 50 (changed unexpectedly)
```

### Can explain what ACID is and why it solves concurrency problems for databases.

ACID ensures reliable and safe transactions in databases, especially when multiple users access data at the same time.

### Properties

- Atomicity
  - A transaction is all or nothing
  - If one part fails, everything is rolled back

- Consistency
  - Data always stays valid according to rules and constraints

- Isolation
  - Transactions do not interfere with each other
  - Prevents concurrency issues (dirty reads, lost updates, etc.)

- Durability
  - Once committed, data is permanently saved

### Why it solves concurrency problems
- Isolation keeps transactions separate
- Atomicity prevents partial updates
- Consistency ensures valid data
- Together, they prevent common issues like dirty reads and lost updates

I can do it!

### Is aware of the possibility to define transactions in SQL and JDBC.

- Transactions allow multiple operations to be treated as a single unit
- Ensures data integrity using COMMIT and ROLLBACK

### SQL Example
```sql
BEGIN;

UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

COMMIT;
--use Roll back if something fails
```


### JDBC Example(java)

```java
Connection conn = dataSource.getConnection();

try {
    conn.setAutoCommit(false);

    // execute queries
    // ...

    conn.commit();
} catch (Exception e) {
    conn.rollback();
} finally {
    conn.setAutoCommit(true);
    conn.close();
}
```

### and atomic structures.
- Atomic = an operation that happens completely or not at all
- No other process can see it half-done

### In Databases
- Atomicity is part of ACID
- Ensures a transaction is fully completed or rolled back

### In Programming (Concurrency)
- Atomic operations prevent race conditions
- Common in multithreading

### Java Example
```java
import java.util.concurrent.atomic.AtomicInteger;

AtomicInteger counter = new AtomicInteger(0);

counter.incrementAndGet(); // atomic operation
```
