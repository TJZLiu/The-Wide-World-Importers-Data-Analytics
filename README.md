The Wide World Importers (WWI) is a wholesales novelty goods importer and distributor operating from the San Francisco bay area. In this assignment we will be working with their database. You can get more information and details about the WWI database in the following link: https://docs.microsoft.com/en-us/sql/samples/wide-world-importers-what-is?view=sql-server-ver15

The focus of the second assignment is modelling. We will use the World Wide Importers database and convert it to a document-based database. To that end, we will be leveraging concepts like data denormalization, indices, and mongodb design patterns.

More information on the extended datamodel to be found here:
https://docs.microsoft.com/en-us/sql/samples/wide-world-importers-oltp-database-catalog?view=sql-server-ver15

Problem Description
Your team has just arrived at WWI (a leading company in logistics). Welcome!
Even though business is thriving, the IT department is going through a bad time.
Digitalization was never a priority for the company and now the company operational and analytical requirements are starting to grow beyond the capabilities of their existing data architecture.

WWI data are spread accross different systems, but we've already managed to pull them all into a mongo dump file. This data file is an exact dump of the SQL data so includes all the same structure, the SQL tables become collections and the rows become documents. This means all the original SQL keys are included in the data.
Currently, the costs to develop the necessary queries to collect data to answer questions asked by the different departments are too high.

Management concluded it is the right time to revise and revamp the data architecture, in order to speed up operations.

In that context, your team was tasked with merging all the company data into a single and coherent Mongo database.
It is expected that, with your solution, WWI will have a better understanding of their business and that the different departments will be able to obtain efficiently the answers they need.

The WWI team shared with you an ERD of their current datamodel:
datamodel

Note You can open the file WWI.png that is in the same directory as this notebook to see the above image in more detail and zoom in as you need.

Addtionally, the WWI team asked you the deliver the following outputs in 4 weeks:

Understand and model the database in MongoDB.
Setup the database so that it is performs well for the queries they have provided. You should include reasoning in comments for the decisions you make on modelling the database.
Answer the questions (queries) on the data provided.
Submit the results by following the instructions.
With these deliveries, you will have created a prototype and allows the management to decide whether MongoDB is a good solution that meets their requirements.

Design Requirements
Note that WWI has the following query requirements for the database.

The web team needs to know:

Which state province do we have the most suppliers in?
How many people have three or more OtherLanguage?
Top 10 most common OtherLanguage for people records.
How many customer records are valid after November 2015?
What percentage of people records don't have the UserPreferences field?
The warehouse group needs to know:

What is the average difference in days between OrderDate and ExpectedDeliveryDate for orders sold by (SalespersonPersonID) person with the name Jack Potter?
Which items get ordered the most in bulk (largest average quantity ordered)?
Which two items get ordered together the most?
For each customer category which 3 items have the ordered the most?
What is the current stock of each stockgroup?
The CFO needs to know:

What is the monthly total order count for each month?
How many orders are there from the customer Tailspin Toys (Head Office)?
What are the average monthly sales prices of all goods sold?
In each state province what is the average customer credit limit?
What are the yearly expenditures with each supplier (per supplier name)?
Partnerships needs to know:

What is the most common payment type?
What percentage of people have their Title as Team Member?
Which supplier of the category Novelty Goods Supplier has the most transactions?
What is the highest CommissionRate that a person has?
The marketing team needs to know:

What is the name of the sales person with the largest sum of invoice values in 2013 (person whose customers paid the most money)?
Who are the most common PickedByPersonID person names for orders done by customer Adriana Pena?
How many people have in their name the string Sara?
What are the top 10 most Common Names (Primary or Surnames) of people?
Transform the mongo dump file provided with this notebook and model a database following mongodb's best practices. You should adjust the data model to best fit the use cases provided above. Think about collections, embedding, linking, indexing, and the patterns learned in class. Provide justifications for each decision you make. What, if any, are the trade-off's or disadvantages of your approach.

Use MongoDB queries to answer the questions on your transformed database.
