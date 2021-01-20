# Postgres 

Postgres is an open-source relational database management system emphasizing extensibility and SQL compliance. In this project I used Postgres to to create a database for a music streaming company called SPARKIFY. The main function of the etl is to enjest JSON data, tranform it into a Star Schema for ease of use and query optimization, and load it into my Postgres database. 

## Use
  1. Run create_table.py
  2. Run etl.py 
  

## Schema Design

This Star Schema includes 1 fact and 4 dimenston tables:

  ### Fact Table: 
   <b>Songplay Table</b>
   
   -  songplay_id serial,
   -  start_time timestamp not null,
   -  user_id INT not null,
   -  level VARCHAR NOT NULL,
   -  song_id VARCHAR(18),
   -  artist_id VARCHAR(18),
   -  session_id INT NOT NULL,
   -  location VARCHAR NOT NULL,
   -  user_agent VARCHAR NOT NULL,
   -  PRIMARY KEY (songplay_id)
    
   ### Dimension Tables:
   
   <b>User Table</b>
     
   -  user_id int,
   -  first_name VARCHAR,
   -  last_name VARCHAR,
   -  gender CHAR(1),
   -  level VARCHAR,
   -  PRIMARY KEY (user_id)
    
   <b>Song Table</b>
    
   -  song_id VARCHAR(18),
   -  title VARCHAR NOT NULL,
   -  artist_id VARCHAR(18) NOT NULL,
   -  year INT NOT NULL,
   -  duration FLOAT NOT NULL,
   -  PRIMARY KEY (song_id)
    
   <b>Artist Table</b>
    
   -  artist_id VARCHAR(18),
   -  name VARCHAR,
   -  location VARCHAR ,
   -  latitude FLOAT,
   -  longitude FLOAT,
   -  PRIMARY KEY (artist_id)
    
   <b>Time Table</b>
    
   -  start_time TIMESTAMP NOT NULL,
   -  hour int NOT NULL,
   -  day int NOT NULL,
   -  week int NOT NULL,
   -  month int NOT NULL,
   -  year int NOT NULL,
   -  weekday int NOT NULL
   
 
 # Apache Cassandra
 
 Using Apache Cassandra, a noSQL database, we will be working with the same music streaming company called sparkify. The purpose of this project folder is to create an etl using this type of database.
 
 
## Project Template

In this project we will be working within a jupyter notebook file. The ouline of this project is as followed:

  1. We will process the event_datafile_new.csv dataset to create a denormalized dataset
  2. We will model the data tables with our queries in mind
  3. We will provide queries that we will need to model the data tables for 
  4. We will load the data into tables we create in Apache Cassandra dn run the queries 
  

## Project Steps
Below are the following steps used to create this project

### Modeling your NoSQL database or Apache Cassandra database
2. Design tables to answer the queries outlined in the project template
3. Write Apache Cassandra CREATE KEYSPACE and SET KEYSPACE statements
4. Develop your CREATE statement for each of the tables to address each question
5. Load the data with INSERT statement for each of the tables
6. Include IF NOT EXISTS clauses in your CREATE statements to create tables only if the tables do not already exist. We recommend you also include DROP TABLE statement for each table, this way you can run drop and create tables whenever you want to reset your database and test your ETL pipeline
7. Test by running the proper select statements with the correct WHERE clause

### Build ETL Pipeline
1. Implement the logic in section Part I of the notebook template to iterate through each event file in event_data to process and create a new CSV file in Python
2. Make necessary edits to Part II of the notebook template to include Apache Cassandra CREATE and INSERT statements to load processed records into relevant tables in your data model
3. Test by running SELECT statements after running the queries on your database
 
 
 
