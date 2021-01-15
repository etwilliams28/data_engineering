# Postgres 

Postgres is an open-source relational database management system emphasizing extensibility and SQL compliance. In this project I used Postgres to to create a database for a music streaming company called SPARKIFY. The main function of the etl is to enjest JSON data, tranform it into a Star Schema for ease of use and query optimization, and load it into my Postgres database. 

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
   
 
