# nosql-challenge
Module 12 Challenge - UWA/edX Data Analytics Bootcamp

Github repository at: [https://github.com/alyssahondrade/nosql-challenge.git](https://github.com/alyssahondrade/nosql-challenge.git)

## Table of Contents
1. [Introduction](https://github.com/alyssahondrade/nosql-challenge/tree/main#introduction)
    1. [Goal](https://github.com/alyssahondrade/nosql-challenge/tree/main#goal)
    2. [Repository Structure](https://github.com/alyssahondrade/nosql-challenge/tree/main#repository-structure)
    3. [Dataset](https://github.com/alyssahondrade/nosql-challenge/tree/main#dataset)
2. [Approach](https://github.com/alyssahondrade/nosql-challenge/tree/main#approach)
3. [Analysis](https://github.com/alyssahondrade/nosql-challenge/tree/main#analysis)


## Introduction

### Goal
The goal of the project is to evaluate food hygiene ratings of establishments across the UK, to assist the journalists and food critics of the food magazine "Eat Safe, Love" in identifying where to focus future articles.

### Repository Structure
Source code:
- [NoSQL_setup.ipynb]() contains the code to setup the database for analysis.
- [NoSQL_analysis.ipynb]() contains the analysis code.

The [`Resources`](https://github.com/alyssahondrade/nosql-challenge/tree/main/Resources) directory contains the dataset: [`establishments.json`](https://github.com/alyssahondrade/nosql-challenge/blob/main/Resources/establishments.json)

### Dataset
- UK Food Standards Agency Links to an external site (2022). Available from: [https://www.food.gov.uk/](https://www.food.gov.uk/)

- UK food hygiene rating data API. Available from: [https://ratings.food.gov.uk/open-data/en-GB](https://ratings.food.gov.uk/open-data/en-GB)


## Approach
1. Import the database using the following code:

    `mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json`

2. Confirm the database and its collections were correctly created.
    - Check the database: `list_database_names()`
    - Check the collections: `list_collection_names()`

3. Confirm the documents exist: `establishments.find_one()`

4. Update the database as per the food magazine's requirements:
    - Add a document for a new, unrated restaurant: `Penang Flavours`.
    - Remove all establishments in `Dover`.

5. Clean the data by converting to the correct datatypes.

## Analysis
1. Which establishments have a hygiene score equal to 20?
    - There are __41__ establishments which meet this criteria.
    - Refer to [NoSQL_analysis.ipynb]() to identify these establishments.

2. Which establishments in London have a `RatingValue` greater than or equal to 4?
    - There are __33__ establishments which meet this criteria.

3. What are the top 5 establishments with a `RatingValue` rating value of 5, sorted by lowest hygiene score, nearest to the new restaurant added `Penang Flavours`?
    - Howe and Co Fish and Chips - Van 17
    - Atlantic Fish Bar
    - Plumstead Manor Nursery
    - Iceland
    - Volunteer

4. How many establishments in each Local Authority area have a hygiene score of 0?
    - There are a total of __55__ local authorities which have an establishment with a hygiene score of 0.
    - Refer to [NoSQL_analysis.ipynb]() to identify the count for each local authority.