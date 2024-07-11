# Question 1:

Build an aggregated table (let us call it the macrotable) indexed by week and country_name containing all relevant information from the whole set of CSV files provided. The resulting table must not contain missing values. The resulting table must contain a variable with the number of deaths.


In other words, every single entry in this macrotable must contain information refered to a specific country in a specific week (inside the range of dates provided by the input files). You can accomplish this goal by aggregating and joining the content of the input tables. Some tips:


    Before starting doing join/aggregation operations, elaborate a brief plan about the sequence of operation you will perfom to obtain the macrotable.
    Analyze every table separatedly to spot inconsistencies or issues to be solved before the joining/aggregation process.
    Granularity of input data is not homogeneous (some table are indexed by time, daily, while others not). Remember that the final table must be indexed by week and country
    In this process, you can (and should!) crearte derived variables from existing ones to enrich the data
    During the process, a lot of missing values can arise (due to data transformations, due to joining operations, etc.). Handle all this missing values. The resulting table must not contain any.
    Do the aggregations at the end of the process. In order to preserve information, first join all data (with the highest granularity), and then do the aggregations to weeks and countries.
    You can take the "epidemiology" table as reference to get the range of dates


This is an example of a macrotable. Use it to figure out how can be the output of this exercise


# Question 2:

Automatize your ETL process within a Python script ready to be executed from the terminal


Build a Python script with all ETL operations defined in the previous question. This script must read input data, execute the ETL process and save the resulting table in CSV format in the specified location. This script must contain the following parameters:


path        (positional) Location of the folder containing the input files
-o          (kw, optional) Output path. Location to save the macrotable file. If not set, macrotable will be stored in the current working directory with name "macrotable.csv"
-start      (kw, optional) The starting date to consider to build the macrotable. If not set, use "2020-01-02".
-end        (kw, optional) The ending date to consider to build the macrotable. If not set, use "2022-08-22".
-countries  (kw, optional) The list of countries to include in the macrotable. If not set, use all countries.


# Question 3 

ntegrate everything with a SQL-like database


In this optional question, you have the oportunity to work with databases in Python. Using your preferred SQL technology (MySQL, PostgreSQL, SQLite, DuckDB, etc.), Modify you ETL script to read data from the DB and store resulting macrotable to the DB.


    In a separate process, or manually, store the input data in the DB.
    Modify your ETL script to read from the DB instead of the CSV files
    Modify your ETL script to write to the DB instead of the CSV files


NOTE: This exercise is optional. My recommendation is that you first do the rest of the exercises (Part I and II), and then return to this one if you want to play with a more real environment.

# Question 4

Elaborate an Exploratory Data Analysis


For this exercise, you can use the resulting data table from the previous part and also the original files. This exploratory data analysis should reveal the relationships between different variables from the dataset as well as derived variables created by you from the original ones. Some tips to follow.


    Create new variables from the original ones
    Be imaginative. Look on the internet about possible charts used to represent your stories.
    Ask questions from the business perspective and try to find the answers using Python
    Use all power of Plotly to represent your insights
    Don't lose the main goal of the problem: predicting death cases


# Submission

A notebook named GroupAssignment_EDA_GroupX.ipynb with all the analysis.


# Evaluation

This part of the assignment holds the 40% of the total assignment score, and it will be peer reviewed during the presentations session. Every student must provide a score (from 0 to 10) to every group, using the following schema.


    Complexity and depth of the analysis of COVID-19 deaths (4 points)
    Look & feel of the charts (interactivity, the axes are labeled, colors are consistent, etc.) (4 points)
    The presentation is well structured and is easy to follow (2 points)


The score of this part will be the average of all scores received from all the students.


NOTE: This part of the assignment is intended to be a role-playing game in which you act as provider of services (presenter), and the customer (listener). Please, be honest with your evaluations.
