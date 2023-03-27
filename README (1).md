# AWS Redshift Data Warehousing using Sparkify data set
In this project, I developed an ETL pipeline for a Redshift-hosted database, loaded data from S3 to Redshift staging tables, and then ran SQL statements to generate the analytical tables from these staging tables.using a psycopg2 as a connection using python.

## Schema for Song Play Analysis
Using the song and event datasets, you'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.

### Fact Table
1. songplays - records in event data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent.

### Dimension Tables
1. users - users in the app
user_id, first_name, last_name, gender, level
2. songs - songs in music database
song_id, title, artist_id, year, duration
3. artists - artists in music database
artist_id, name, location, lattitude, longitude
4. time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday

# Project Files:
**sql_queries.py** have all sql queries in that wil be use in the create table .

**create_tables.py** using queries written in sql. you'll create your fact and dimension tables for the star schema in Redshift.

**etl.py** load the data from S3 into staging tables on Redshift and then process it into analytics tables on Redshift aws.

**dwh.cfg** have the AWS connection variables and configurations.

# Project steps
1. Design data base schema

2. Write a SQL  queries to CREATE  tables in sql_queries.py

3. Write SQL DROP statements to drop tables in the beginning of create_tables.py if the tables already exist.This way, you can run create_tables.py whenever you want to reset your database and test your ETL pipeline.

4. connecting to database in the AWs.

5. Launch a redshift cluster and create an IAM role that has read access to S3.

6. Add redshift database and IAM role info to dwh.cfg.

7. develop the ETL pipeline.

8. Test by running create_tables.py and checking the table schemas in your redshift database. You can use Query Editor in the AWS Redshift console for this.
