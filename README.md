## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
    - [Windows](#windows)
    - [macOS](#macos)
3. [Setting up MongoDB Compass](#setting-up-mongodb-compass)
4. [CRUD Operations in MongoDB](#crud-operations-in-mongodb)
    - [Create](#create)
    - [Read](#read)
    - [Update](#update)
    - [Delete](#delete)
5. [Additional Resources](#additional-resources)

## Introduction
This guide provides step-by-step instructions for installing MongoDB on various operating systems and performing basic CRUD (Create, Read, Update, Delete) operations using MongoDB Compass, a graphical user interface for MongoDB.

## Installation

### Windows
1. **Download MongoDB**:
   - Visit the [MongoDB Download Center](https://www.mongodb.com/try/download/community) and download the Windows installer.
   
2. **Run the Installer**:
   - Follow the prompts in the MongoDB installer. Choose "Complete" setup.
   
3. **Set up Environment Variables**:
   - Add the MongoDB bin directory to your system's PATH. Typically, the path is `C:\Program Files\MongoDB\Server\<version>\bin`.

4. **Start MongoDB**:
   - Open Command Prompt and run `mongod` to start the MongoDB server.

### macOS
1. **Install Homebrew**:
   - If you don't have Homebrew, install it by running:
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```
   
2. **Install MongoDB**:
   - Run the following command to install MongoDB:
     ```bash
     brew tap mongodb/brew
     brew install mongodb-community
     ```
   
3. **Start MongoDB**:
   - Start MongoDB with:
     ```bash
     brew services start mongodb/brew/mongodb-community
     ```

## Setting up MongoDB Compass
1. **Download MongoDB Compass**:
   - Visit the [MongoDB Compass Download page](https://www.mongodb.com/products/compass) and download the installer for your operating system.
   
2. **Install MongoDB Compass**:
   - Follow the instructions to install MongoDB Compass on your system.
   
3. **Connect to MongoDB**:
   - Open MongoDB Compass.
   - In the connection window, enter the following details (if running locally with default settings):
     - Hostname: `localhost`
     - Port: `27017`
   - Click on "Connect".

## CRUD Operations in MongoDB

### Create

SYNTAX : db.createCollection( “<collection_name>“):

CREATING A COLLECTION USING TERMINAL:

COLLECTION NAME

```javascript
db.createCollection( "authors")
```
To insert a document into a collection, use the `insertOne` method. Below is an example of inserting a document into a `authors` collection:

```javascript
db.authors.insertOne(
	{  _id: 1,
	   name: "J.K. Rowling", 
	   nationality: "British", 
	   age: 56, 
	   notable_works: ["Harry Potter series", 
		       "The Casual Vacancy"]  
	}, 
	{writeConcern: {w: "majority"}})

```
To insert multiple documents at once, use the insertMany method. Below is an example of inserting multiple documents into the users collection:
```javascript
db.authors.insertMany([
	{  _id: 2,
	   name: "George R.R. Martin", 
	   nationality: "American", 
	   age: 37, 
	   notable_works: ["A Song of Ice and Fire series"]  
	},
	{  _id: 3,
	   name: "Agatha Christie", 
	   nationality: "British", 
	   age: 60, 
	   notable_works: ["Murder on the Orient Express",
		       "The Murder of Roger Ackroyd"]  
	}],
	{writeConcern: {w: "majority"},
	ordered: false})
```

## Read

To query documents from a collection, use the find method. Below is an example of querying all documents in the authors collection:

```javascript
db.authors.find()
```
To find documents with a specific field value, find the author whose age is $lt (less than) 50 :

```javascript
db.authors.find(
	{
		age:{$lt:50}
	})
```
## Update

To update a document, use the updateOne method. Below is an example of updating the age of the user with the name "J.K Rowling":
```javascript
db.authors.updateOne(
  { name: "J.K. Rowling" },
  { $set: { age: 30 } }
)

```
To update multiple documents, use the updateMany method:
```javascript
db.authors.updateMany(
  { age: { $gt: 59 } },
  { $set: { nationality : "Indian" } }
)

```
## Delete

To delete a document, use the deleteOne method. Below is an example of deleting the user with the name "Agatha Christie":
```javascript
db.authors.deleteOne({ "name": "Agatha Christie" })
```
To delete multiple documents, use the deleteMany method:
```javascript
db.authors.deleteMany({ nationality : "British" })
```
## Additional Resources
- [MongoDB Documentation](https://docs.mongodb.com/)
- [MongoDB Compass Documentation](https://docs.mongodb.com/compass/current/)
- [MongoDB University](https://university.mongodb.com/)
