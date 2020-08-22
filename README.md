SQL4DataScience: A practical use of foundational SQL skills

Module 1: Practice Quiz
-
1.) Retrieve all the data from the tracks table. Who is the composer for track 18? AC/DC

      SELECT *
      FROM Tracks;

2.) Retrieve all data from the artists table. Look at the list of artists, how many artists are you familiar with (there is no wrong answer here)?

      SELECT *
      FROM Artists;

3.) Retrieve all data from the invoices table. What is the billing address for customer 31? 194A Chain Lake Drive

      SELECT *
      FROM Invoices;

4.) Return the playlist id, and name from the playlists table. How many playlists are there? Which would you classify is your favorite from this list? There are 18 playlists, 90's music is my favorite. 

      SELECT Playlistid
        ,Name
      FROM Playlists;

5.) Return the Customer Id, Invoice Date, and Billing City from the Invoices table. What city is associated with Customer ID number 42? What was the invoice date for the customer in Santiago? Bordeaux is the city associated with CustomerId 42, and the invoice date for the customer in Santiago was 2009-04-04 00:00:00  

      SELECT CustomerId
        ,InvoiceDate
        ,BillingCity
      FROM Invoices;

6.) Return the First Name, Last Name, Email, and Phone, from the Customers table. What is the telephone number for Jennifer Peterson?  
+1 (604) 688-2255

      SELECT FirstName
        ,LastName
        ,Email
        ,Phone
      FROM Customers;

7.) Return the Track Id, Genre Id, Composer, Unit Price from the Tracks table. How much do these tracks cost?  0.99

      SELECT TrackId
        ,GenreId
        ,Composer
        ,UnitPrice
      FROM Tracks;

8.) Select all the columns from the Playlist Track table and limit the results to 10 records. How might this information be used? This information can be used to see which tracks are associated with the playlist. 

      SELECT *
      FROM Playlist_track Limit 10;

9.) Select all the columns from the Media Types table and limit the results to 50 records. What happened when you ran this query? Were you able to get all 50 records? There is only 5 rows in the Media_types table. 

      SELECT *
      FROM Media_types Limit 50;

10.) Select all the columns from the Albums table and limit the results to 5 records. How many columns are in the albums table? Plays Metallica By Four Cellos

      SELECT *
      FROM Albums;

Module 1: Coding Questions
-
1.) Retrieve all the records from the Employees table.What is Robert King's mailing address? Note: You will have to scroll to the right in order to see it. 590 Columbia Boulevard West, Lethbridge, AB, CANADA T1K 5N8

      Select *
      From (employees);

2.) Retrieve the FirstName, LastName, Birthdate, Address, City, and State from the Employees table. Which of the employees listed below has a birthdate of 3-3-1965? Steve

      SELECT (FirstName)
        ,(LastName)
        ,(Birthdate)
      FROM (Employees);

3.) Retrieve all the columns from the Tracks table, but only return 20 rows.What is the runtime in milliseconds for the 5th track, entitled "Princess of the Dawn"? Note: You will need to scroll to the right to see it, and you may want to copy and paste the number to ensure it is entered correctly. 375418

      SELECT *
      FROM (Tracks) Limit 20;

Module 2: Practice Quiz
-

1.) This question is just a formality to ensure the user understands where to get the need info to write the queries. 

2.) Find the distinct values for the extended step. The code has been started for you, but you will need to program the third line yourself before running the query. Which of the following values is not a distinct value? 5

      SELECT DISTINCT Extended_step
      FROM salary_range_by_job_classification
      ORDER BY Extended_step

3.) Excluding $0.00, what is the minimum bi-weekly high rate of pay (please include the dollar sign and decimal point in your answer)? The code has been started for you, but you will need to add onto the last line of code to get the correct answer. $100.00

      SELECT min(Biweekly_high_Rate)
      FROM salary_range_by_job_classification
      WHERE (Biweekly_high_rate) <> '$0.00'

4.) What is the maximum biweekly high rate of pay (please include the dollar sign and decimal point in your answer)? The code has been started for you, but you will need to add onto the last line of code to get the correct answer. $9726.38

      SELECT Max(Biweekly_high_Rate)
      FROM salary_range_by_job_classification

5.) What is the pay type for all the job codes that start with '03'? The code has been started for you, but you will need to program the fourth and fifth lines yourself before running the query. B

      SELECT job_code
        ,pay_type
      FROM salary_range_by_job_classification
      GROUP BY job_code

6.) Run a query to find the Effective Date (eff_date) or Salary End Date (sal_end_date) for grade Q90H0? The code has been started for you, but you will need to program the third through the sixth lines yourself before running the query. 12/26/2009 12:00:00 AM

      SELECT grade
        ,eff_date
        ,sal_end_date
      FROM salary_range_by_job_classification
      WHERE grade = 'Q90H0'

7.) Sort the Biweekly low rate in ascending order. There is no starter code, as you need to write and run the query on your own. Hint: there are 4 lines to run this query. Is this sorted correctly? No

      SELECT Biweekly_Low_Rate
      FROM salary_range_by_job_classification
      ORDER BY Biweekly_Low_Rate ASC;

8.) Write and run a query, with no starter code to answer this question: What Step are Job Codes 0110-0400? Hint: there are 6 lines to run this query. 1

      SELECT Job_Code
        ,Step
      FROM salary_range_by_job_classification
      WHERE Job_Code BETWEEN '0110'
          AND '0400'
      ORDER BY Job_Code ASC;

9.) Write and run a query, with no starter code or hints to answer this question: What is the Biweekly High Rate minus the Biweekly Low Rate for job Code 0170? $0.00

      SELECT Job_Code
        ,Biweekly_High_Rate
        ,Biweekly_Low_Rate
      FROM salary_range_by_job_classification
      WHERE Job_Code = '0170'

10.) Write and run a query, with no starter code or hints to answer this question: What is the Extended Step for Pay Types M, H, and D?0

      SELECT Extended_Step
        ,Pay_Type
      FROM salary_range_by_job_classification
      WHERE Pay_Type = 'M'
        OR Pay_Type = 'H'
        OR Pay_Type = 'D'

11.) Write and run a query, with no starter code or hints to answer this question: What is the step for Union Code 990 and a Set ID of SFMTA or COMMN? 1

      SELECT SetID
        ,Step
        ,Union_Code
      FROM salary_range_by_job_classification
      WHERE (
          SetID = 'COMMN'
          OR SetID = 'SFMTA'
          )
        AND Union_Code = '990'

Module 2: Coding Questions
-
1.) Find all the tracks that have a length of 5,000,000 milliseconds or more. How many tracks are returned? 2

      SELECT Count(TrackID) AS Num_of_Tracks
      FROM Tracks
      WHERE Milliseconds >= 5000000

2.) Find all the invoices whose total is between $5 and $15 dollars.While the query in this example is limited to 10 records, running the query correctly will indicate how many total records there are - enter that number below. 168

      SELECT Count(InvoiceID) AS Num_of_Invoices
      FROM Invoices
      WHERE Total BETWEEN 5
          AND 15

3.) Find all the customers from the following States: RJ, DF, AB, BC, CA, WA, NY. What company does Jack Smith work for? Microsoft Corp

      SELECT FirstName
        ,LastName
        ,Company
        ,STATE
      FROM Customers
      WHERE (
          STATE = 'RJ'
          OR STATE = 'DF'
          OR STATE = 'AB'
          OR STATE = 'BC'
          OR STATE = 'CA'
          OR STATE = 'WA'
          OR STATE = 'NY'
          )
        AND FirstName = 'Jack'
        AND LastName = 'Smith'

4.) Find all the invoices for customer 56 and 58 where the total was between $1.00 and $5.00. What was the invoice date for invoice ID 315? 10-27-2012

      SELECT InvoiceID
        ,InvoiceDate
        ,CustomerID
        ,Total
      FROM Invoices
      WHERE InvoiceID = '315'
        AND (
          CustomerID = '56'
          OR CustomerID = '58'
          )

5.) Find all the tracks whose name starts with 'All'. While only 10 records are shown, the query will indicate how many total records there are for this query - enter that number below. 15

      SELECT Count(Name) AS Starts_with_All
      FROM Tracks
      WHERE Name LIKE 'All%'

6.) Find all the customer emails that start with "J" and are from gmail.com. Enter the one email address returned (you will likely need to scroll to the right) below. jubarnett@gmail.com 

      Select CustomerID
      ,Email
      From Customers
      Where (Email like 'J%')
      And Email like '%gmail.com%'

7.) Find all the invoices from the billing city Brasília, Edmonton, and Vancouver and sort in descending order by invoice ID. What is the total invoice amount of the first record returned? Enter the number below without a $ sign. Remember to sort in descending order to get the correct answer. 13.86 

      SELECT InvoiceID
        ,BillingCity
        ,Total
      FROM Invoices
      WHERE (
          BillingCity = 'Brasília'
          OR BillingCity = 'Edmonton'
          OR BillingCity = 'Vancouver'
          )
      ORDER BY InvoiceID DESC;

8.) Show the number of orders placed by each customer (hint: this is found in the invoices table) and sort the result by the number of orders in descending order. What is the number of items placed for the 8th person on this list? Enter that number below. 7 

      SELECT CustomerID
        ,Count(InvoiceID) AS NumOfOrders
      FROM Invoices
      GROUP BY CustomerID
      ORDER BY NumOfOrders DESC;

9.) Find the albums with 12 or more tracks.While the number of records returned is limited to 10, the query, if run correctly, will indicate how many total records there are. Enter that number below. 158

      Select AlbumID
      ,Count(*) AS numoforders
      From Tracks
      Group By AlbumID
      Having Count(*) >= 12

Module 3: Practice Quiz
-
1.) How many albums does the artist Led Zeppelin have? 14

      SELECT count(AlbumId) AS TotalAlbums
      FROM albums
      WHERE Artistid = (
                  SELECT Artistid
                  FROM artists
                  WHERE name = 'Led Zeppelin'
                  )
2.) Create a list of album titles and the unit prices for the artist "Audioslave". How many records are returned? 40

      SELECT artists.Artistid
            ,artists.Name
            ,albums.Title
            ,tracks.Name
            ,invoice_items.UnitPrice
      FROM artists
      LEFT JOIN albums ON artists.Artistid = albums.Artistid
      LEFT JOIN tracks ON albums.Albumid = tracks.Albumid
      LEFT JOIN invoice_items ON tracks.Trackid = invoice_items.Trackid
      WHERE artists.Name = 'Audioslave'

3.) Find the first and last name of any customer who does not have an invoice. Are there any customers returned from the query? No

      SELECT customers.FirstName
            ,customers.LastName
            ,invoices.invoiceId
      FROM customers
      LEFT JOIN invoices ON customers.CustomerId = invoices.CustomerId
      WHERE invoices.CustomerId = NULL

4.) Find the total price for each album. What is the total price for the album “Big Ones”? 14.85 

      SELECT DISTINCT albums.AlbumId
            ,albums.Title
            ,Sum(tracks.UnitPrice) AS Total
      FROM Albums
      LEFT JOIN tracks ON albums.AlbumId = tracks.AlbumId
      GROUP BY albums.Title
      ORDER BY albums.AlbumId

5.) How many records are created when you apply a Cartesian join to the invoice and invoice items table? 922880

      SELECT invoices.InvoiceId
            ,invoice_items.TrackId
            ,invoice_items.UnitPrice
      FROM invoices
      CROSS JOIN invoice_items

Module 3: Coding Questions
-
1.) Using a subquery, find the names of all the tracks for the album "Californication". What is the title of the 8th track? Porcelain

      SELECT TrackId
            ,Name
      FROM Tracks
      WHERE AlbumId IN (
                  SELECT AlbumId
                  FROM Albums
                  WHERE Title = 'Californication'
                  )
      ORDER BY TrackId

2.) Find the total number of invoices for each customer along with the customer's full name, city and email.After running the query described above, what is the email address of the 5th person, František Wichterlová? Enter the answer below (feel free to copy and paste). frantisekw@jetbrains.com

      SELECT Customers.CustomerId
            ,Customers.FirstName
            ,Customers.LastName
            ,Customers.City
            ,Customers.Email
            ,SUM(InvoiceID) AS Total_Invoices
      FROM Customers
      LEFT JOIN Invoices ON Customers.CustomerId = Invoices.CustomerId
      WHERE Customers.FirstName = 'František'
            AND Customers.LastName = 'Wichterlová'
      GROUP BY Customers.CustomerId

3.) Retrieve the track name, album, artistID, and trackID for all the albums. What is the song title of trackID 12 from the "For Those About to Rock We Salute You" album? Enter the answer below. Breaking The Rules 

      SELECT Tracks.Name
            ,Albums.Title
            ,Artists.ArtistId
            ,Tracks.TrackId
      FROM Albums
      LEFT JOIN Tracks ON Albums.AlbumId = Tracks.AlbumId
      LEFT JOIN Artists ON Albums.ArtistId = Artists.ArtistId
      WHERE Tracks.TrackId = '12'

4.) Retrieve a list with the managers last name, and the last name of the employees who report to him or her. After running the query described above, who are the reports for the manager named Mitchell (select all that apply)? Callahan, King

      SELECT Employees.EmployeeId
            ,Employees.LastName AS Employees
            ,Employees.ReportsTo AS Manager
            ,Employees.Title
      FROM Employees

5.) Find the name and ID of the artists who do not have albums. After running the query described above, two of the records returned have the same last name. Enter that name below. Gilberto

      SELECT Artists.ArtistId
            ,Artists.Name
            ,Albums.Title
      FROM Artists
      LEFT JOIN Albums ON Artists.ArtistId = Albums.ArtistId
      WHERE Albums.Title IS NULL

6.) Use a UNION to create a list of all the employee's and customer's first names and last names ordered by the last name in descending order. After running the query described above, determine what is the last name of the 6th record? Enter it below. Remember to order things in descending order to be sure to get the correct answer. Taylor 

      SELECT FirstName
            ,LastName
      FROM Employees

      UNION

      SELECT FirstName
            ,LastName
      FROM Customers
      ORDER BY LastName DESC;

7.) See if there are any customers who have a different city listed in their billing city versus their customer city. Indicate your answer below. No customers have a different city listed in their billing city versus customer city.

      SELECT Customers.CustomerID
            ,Customers.City
            ,BillingCity
      FROM Customers
      LEFT JOIN Invoices ON Customers.CustomerId = Invoices.CustomerID
      WHERE Customers.City != Invoices.BillingCity
