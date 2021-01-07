# Sparkify-ETL-Database
=======
## Purpose of Project
The database has been built to serve the purpose of analyzing songs that users are listening on the music streaming app. This project has scripts to create database tables according to the desired schema, loads data from JSON files and inserts into tables. Only neccessary information of users, songs and artists that are required for analysis are loaded.

## Tools used
- Database:  PostgreSQL
- Language: Python 3.6.3


## Files description
1. sql_queries.py : Contains all required queries for the ETL process.
2. create_tables.py : Connects to sparkifydb and creates/resets data tables. It runs the create table queries in sql_queries.py
3. etl.ipynb : Python notebook that has loads data from a single file in song_data and log_data. Used to intuitively build the ETL pipeline.
4. etl.py : Loads data from all JSON files in song_data and log_data through ETL pipeline and fills the tables.
5. test.ipynb : Has scripts that are run to test the ETL pipeline by loading contents of the table.

## Data files
1. song_data : Contains song data files in JSON format. Each file contains JSON data of a single song.
2. log_data : Contains user activity logs from the app. Each file contains the event logs for an entire day.



## Schema Design and ETL
- Fact table: songplays table
- Dimension table: users, songs, artists, time

The fact table contains keys for these table along with level of user, location of user and user agent i.e device/browser used.

A STAR schema is implemented here as it is denormailzed and hence favourable for OLAP qureies. Raw data is present in the form of JSON files in song_data and log_data. The ETL pipeline loads data from these JSON files and fills the database tables.

![alt text](https://github.com/VinithAngadi/Sparkify-ETL-Database/blob/main/Images/UML_diagram-3.png)




## Instructions to run the project

- Requirements: Python 3, PostgreSQL, Jupyter notebook, Terminal/Command line
- Steps:
    Step 1: Run the create_tables.py using 'python3 create_tables.py' command.This connects to database and creates tables.
    Step 2: Run etl.py using 'python3 etl.py' command. This performs the ETL process and fills the tables and closes the connection to database.
    Step 3: Test the pipeline by running all the cells of test.ipynb in jupyter notebook. Contents of all the tables will be dosplayed here.
