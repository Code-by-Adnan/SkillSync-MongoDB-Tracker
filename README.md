# SkillSync: IT Student & Project Tracker

SkillSync is a NoSQL-based database system designed to manage and analyze IT student profiles. Moving beyond traditional row-and-column relational databases, this project leverages MongoDB's document-oriented architecture to track dynamic student data, including academic courses, arrays of technical skills, and the number of projects each student has completed.

This repository contains a dataset of 50 sample student records and the source code for 34 database queries: 23 queries demonstrating essential Create, Read, Update, and Delete (CRUD) operations, and 11 advanced queries covering indexing, aggregation pipelines, and schema validation.

## Key Features

- **Document-Based Storage:** Utilizes flexible JSON-like documents to store complex data types, such as skill arrays, without needing separate relational tables.
- **Advanced Querying:** Implements logical and comparison operators to filter students based on project completion rates and specific skill combinations.
- **Array Manipulation:** Demonstrates how to dynamically add or remove technical skills from a student's profile using MongoDB's array update operators.
- **Data Sorting & Limiting:** Showcases techniques to organize output data in ascending or descending order for reporting purposes.
- **Indexing & Performance:** Creates single-field, multikey, and compound indexes, and uses `explain("executionStats")` to verify that queries use an index scan instead of a full collection scan.
- **Aggregation Analytics:** Uses multi-stage aggregation pipelines to compute average projects per course, the most common skills, and the distribution of students by city.
- **Schema Validation:** Enforces data integrity with a `$jsonSchema` validator that rejects documents with missing fields, wrong data types, empty skill lists, or negative project counts.

## MongoDB Operators Used

This project extensively utilizes MongoDB's built-in operators to manipulate and retrieve data efficiently:

### Comparison Operators

- `$eq` (Equal To): Matches values that are exactly equal to a specified value.
- `$gt` (Greater Than): Matches values strictly greater than a specified value.
- `$lt` (Less Than): Matches values strictly less than a specified value.
- `$gte` (Greater Than or Equal To): Matches values greater than or equal to a specified value.
- `$lte` (Less Than or Equal To): Matches values less than or equal to a specified value.

### Logical Operators

- `$and`: Joins query clauses with a logical AND to return documents matching all conditions.
- `$or`: Joins query clauses with a logical OR to return documents matching any of the conditions.

### Array Operators

- `$in`: Matches any of the values specified in an array.
- `$all`: Matches arrays that contain all elements specified in the query.
- `$push`: Appends a specified value to an array.
- `$pull`: Removes all array elements that match a specified query.

### Update Operators

- `$set`: Replaces the value of a field with the specified value.
- `$inc`: Increments the value of the field by the specified amount.

### Aggregation Stages and Accumulators

- `$match`: Filters documents before they enter the next pipeline stage.
- `$unwind`: Splits an array field into one document per array element.
- `$group`: Groups documents by a key and computes values for each group.
- `$sort` and `$limit`: Order the pipeline output and restrict how many results are returned.
- `$sum`, `$avg`, `$push`: Accumulators used inside `$group` to count, average, and collect values.

### Indexing and Validation

- `createIndex()`: Builds single-field, multikey (on the `skills` array), and compound indexes.
- `explain("executionStats")`: Shows the query plan and confirms whether an index was used.
- `$jsonSchema` with `collMod`: Adds a validation schema to the existing collection.

## Repository Contents

- `Students_database.json`: The JSON array containing 50 mock IT student profiles used to populate the database.
- `skillsync_mongodb_queries.txt`: Queries 1 to 23, with explanatory comments, covering database and collection creation, CRUD operations, updates, filtering, sorting, and limiting.
- `skillsync_advanced_queries.txt`: Queries 24 to 34, with explanatory comments, covering indexing, aggregation pipelines, and schema validation.
- `Adnan_Ahmad_NoSQL Project Report.pdf`: The project documentation detailing the project's objectives, architecture, and query outputs.

## Query Overview

| Queries | Category | Description |
|---------|----------|-------------|
| 1-3 | Setup | Create the database and collection, and insert records |
| 4-14 | Read | Retrieve and filter data using comparison, logical, and array operators |
| 15-18 | Update | Modify fields and arrays with `$set`, `$inc`, `$push`, and `$pull` |
| 19-20 | Delete | Remove single and multiple records |
| 21-23 | Sort and limit | Order and restrict query results |
| 24-28 | Indexing | Create indexes and verify them with `explain()` |
| 29-32 | Aggregation | Analytics using `$match`, `$unwind`, `$group`, `$sort`, and `$limit` |
| 33-34 | Schema validation | Add a `$jsonSchema` validator and test it with an invalid insert |

## Technologies Used

- MongoDB (NoSQL document database)
- MongoDB Compass (GUI for connecting and importing data)
- MongoSH (MongoDB Shell)
- JSON / BSON
- Git and GitHub

## Getting Started

1. Clone this repository to your local machine.
2. Open MongoDB Compass and connect to your local or cloud database environment.
3. Create a new database named `skillsync` and a collection named `students`.
4. Click **Add Data > Import File** in MongoDB Compass and select `Students_database.json` to populate the database.
5. Open the built-in MongoSH terminal and paste the commands from `skillsync_mongodb_queries.txt` (queries 1 to 23) to test the CRUD operations.
6. Paste the commands from `skillsync_advanced_queries.txt` (queries 24 to 34) to test indexing, aggregation, and schema validation.

**Notes:**
- Queries 15 to 20 modify or delete records. To restore the original 50 records, drop the collection and re-import `Students_database.json`.
- Query 34 is an intentionally invalid insert. It is expected to fail with `MongoServerError: Document failed validation`, which confirms the validator in query 33 is working.

**Author:** Adnan Ahmad
**GitHub:** [Code-by-Adnan](https://github.com/Code-by-Adnan)
