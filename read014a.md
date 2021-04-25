# Database normalization

* Database normalization is a process used to organize a database into tables and columns. The idea is that a table should be about a specific topic and that only those columns which support that topic are included

* By limiting a table to one purpose, you reduce the number of duplicate data that is contained within your database, which helps eliminate some issues stemming from database modifications. 

## Reasons for Normalization

1. to minimize duplicate data which Duplicated information presents two problems
*It increases storage* and *decreases performance.* and *It becomes more difficult to maintain data changes.*

2.  to minimize or avoid data modification issues

3. to simplify queries

**There are three modification anomalies that can occur**

1. Insert Anomaly

2. Update Anomaly

3. Deletion Anomaly

## Definition of Normalization

1. First Normal Form – The information is stored in a relational table and each column contains atomic values, and there are not repeating groups of columns.

2. Second Normal Form – The table is in first normal form and all the columns depend on the table’s primary key.

3. third Normal Form – The table is in second normal form and all of its columns are not transitively dependent on the primary key.