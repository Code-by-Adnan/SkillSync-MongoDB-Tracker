# SkillSync: IT Student & Project Tracker
SkillSync is a NoSQL-based database system designed to manage and analyze IT student profiles. Moving beyond traditional row-and-column relational databases, this project leverages MongoDB's document-oriented architecture to track dynamic student data, including academic courses, nested arrays of technical skills, and completed project portfolios.

This repository contains the complete dataset of 50 student records and the source code for 23 distinct database queries demonstrating essential Create, Read, Update, and Delete (CRUD) operations.

## Key Features
* Document-Based Storage: Utilizes flexible JSON-like documents to store complex data types, such as skill arrays, without needing separate relational tables.

* Advanced Querying: Implements logical and comparison operators to filter students based on project completion rates and specific skill combinations.

* Array Manipulation: Demonstrates how to dynamically add or remove technical skills from a student's profile using MongoDB's array update operators.

* Data Sorting & Limiting: Showcases techniques to organize output data in ascending or descending order for reporting purposes.

## MongoDB Operators Used
This project extensively utilizes MongoDB's built-in operators to manipulate and retrieve data efficiently:

### Comparison Operators
* $eq (Equal To): Matches values that are exactly equal to a specified value.

* $gt (Greater Than): Matches values strictly greater than a specified value.

* $lt (Less Than): Matches values strictly less than a specified value.

* $gte (Greater Than or Equal To): Matches values greater than or equal to a specified value.

* $lte (Less Than or Equal To): Matches values less than or equal to a specified value.

### Logical Operators
* $and: Joins query clauses with a logical AND to return documents matching all conditions.

* $or: Joins query clauses with a logical OR to return documents matching any of the conditions.

### Array Operators
* $in: Matches any of the values specified in an array.

* $all: Matches arrays that contain all elements specified in the query.

* $push: Appends a specified value to an array.

* $pull: Removes all array elements that match a specified query.

### Update Operators
* $set: Replaces the value of a field with the specified value.

* $inc: Increments the value of the field by the specified amount.

## Repository Contents
* students_dataset.json: The complete JSON array containing 50 mock IT student profiles used to populate the database.

* queries.js: The source file containing 23 sequentially numbered MongoDB commands with explanatory comments for executing CRUD operations, updates, and advanced filtering.

* Project_Report.pdf: The official documentation detailing the project's objectives, architecture, and query outputs.

## Getting Started
1. Clone this repository to your local machine.

2. Open MongoDB Compass and connect to your local or cloud database environment.

3. Create a new database named skillsync and a collection named students.

4. Click Add Data > Import File in MongoDB Compass and select students_dataset.json to populate the database.

5. Open the built-in MongoSH terminal and paste the commands from queries.js to test the operations.

**Author:** Adnan Ahmad

**GitHub:** Code-by-Adnan
