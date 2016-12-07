# sqlmap

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

Step 4: Dump Database Tables
```
sqlmap -u URL -D <database> -T <table> --dump
```
