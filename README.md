# Project: Data Modeling with Postgres

## Document Purpose
This document outlines the detailed technical requirements and design for the creation of PostgreSQL database for storing the data generated from the streaming music startup - Sparkify.

## Overview
Core of the data that is generated by the streaming app Sparkify is songs data (data/songs_data path) and logs by the user access (data/logs_data). All the files generated are in the form of JSON file type. ETL Solution is designed to perform the data ingestion.

This document outlines the following things -
### Sparkify Database Schema
### ETL Solution for data loading into Sparkify db

## Sparkify Database Schema
### Description
In order to perform proper analytics on the data, datawarehouse design is proposed to perform the data ingestion. 

### Fact Table
##### songplays - records in log data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables
##### users - users in the app
user_id, first_name, last_name, gender, level
##### songs - songs in music database
song_id, title, artist_id, year, duration
##### artists - artists in music database
artist_id, name, location, lattitude, longitude
##### time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday

### ETL Solution for data loading into Sparkify db
Using Python along with the associate libraries such as numpy and pandas the ETL solution is designed.
In order to execute the ETL, use the terminal and run the following command -

python etl.py