**Estimated Time to complete : 3h (+ ~30 minutes)**

Pre-requisites
----------------------


-   You would  need access to the database (see the Database section below for details) and utilize the necessary JDBC drivers. 
-   You are free to choose the format of your REST endpoints (URIs)
-   Be sure to follow the best practices for coding and also add any related unit tests. The code should be as close to the production-ready code as possible.

Steps
-----

1.  Review the file usernames.txt that contains a list of usernames.
2.  Create a REST web service in Java (Spring Boot or similar framework) that reads this file and  returns a valid JSON response with the list of users in a meaningful format.
3.  For the web service created above, if we append  '/save' to the URI, the web service should persist the data from the file into the database and return a simple text response saying "Saved n usernames", where n is the number of usernames in the file. You can either use plain JDBC to save the data, or an ORM tool like Hibernate. (Bonus points for using an ORM tool)
4.  Create another REST webservice say getUserNamesFromDB, which when called will retrieve all the usernames stored in the database at a given point of time.
5.  Share your results using tool like Postman or Curl (available in the Terminal section).
6.  From the "Workspace" menu, select "Download as Zip" and provide it to the person co-ordinating the interview. 
6.  Bonus points: Javascript/jQuery related task : Create a simple user interface in HTML that has a button labelled "Get User Names". When this button is clicked, it should make an AJAX call to the web service you created in #4 above AND display the usernames in a simple HTML table.
7.  Bonus points: What if we want to search for specific usernames stored in the database? Add a "filter" option to the web service getUserNamesFromDB so that the response only includes usernames that match this filter value. For example: If value passed in "filter" is "abc", it should only match usernames that contain "abc".


Database
--------

- Connection details - make sure you have postgres client installed in your machine.
- JDBC URL (also contains the password) : Ask the interviewer for it.
- The Users table already exists in the database and was created using the steps below:

```
$ psql -h stampy.db.elephantsql.com -p 5432 -U zcxfobqy
Password for user zcxfobqy:
psql (9.5.14, server 9.6.2)
WARNING: psql major version 9.5, server major version 9.6.
Some psql features might not work.
SSL connection (protocol: TLSv1.2, cipher: ECDHE-RSA-AES128-GCM-SHA256, bits: 128, compression: off)
Type "help" for help.
zcxfobqy=> \dt
No relations found.
zcxfobqy=> CREATE TABLE Users ( username VARCHAR (50) NOT NULL);
CREATE TABLE
zcxfobqy=> select * from Users;
username
----------
(0 rows)
zcxfobqy=> INSERT INTO Users (username) VALUES ('xyz');
INSERT 0 1
zcxfobqy=> select * from Users;
username
----------
xyz
(1 row)
```



