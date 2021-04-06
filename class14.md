# read 14a: DB Normalization

Database normalization is a process used to organize a database into tables and columns.  The main idea with this is that a table should be about a specific topic and only supporting topics included. Take a spreadsheet containing the information as an example, where the data contains salespeople and customers serving several purposes:

* Identify salespeople in your organization
* List all customers your company calls upon to sell a product
* Identify which salespeople call on specific customers.



## Reasons for Database Normalization
Three main reasins:

The first is to minimize duplicate data, the second is to minimize or avoid data modification issues, and the third is to simplify queries. 


## Search and Sort Issues

The last reason weâ€™ll consider is making it easier to search and sort your data.  In the SalesStaff table if you want to search for a specific customer such as Ford, you would have to write a query like :

```
SELECT SalesOffice
FROM SalesStaff
WHERE Customer1 = â€˜Fordâ€™ OR
      Customer2 = â€˜Fordâ€™ OR
      Customer3 = â€˜Fordâ€™
```

Clearly if the customer were somehow in one column our query would be simpler.  Also, consider if you want to run a query and sort by customer. 

Our current table makes this tough. You would have to use three separate UNION queries! You can eliminate or reduce these anomalies by separating the data into different tables. This puts the data into tables serving a single purpose.

The process to redesign the table is database normalization.


## Definition of Database Normalization

* First Normal Form â€“ The information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns.
* Second Normal Form â€“ The table is in first normal form and all the columns depend on the tableâ€™s primary key.
* Third Normal Form â€“ the table is in second normal form and all of its columns are not transitively dependent on the primary key
