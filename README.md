# MongoDB Installation and CRUD Operations Guide

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
    - [Windows](#windows)
    - [macOS](#macos)
    - [Linux](#linux)
3. [Setting up MongoDB Compass](#setting-up-mongodb-compass)
4. [CRUD Operations in MongoDB Compass](#crud-operations-in-mongodb-compass)
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

### Linux
1. **Import the MongoDB public GPG Key**:
   - Run:
     ```bash
     wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
     ```
   
2. **Create a list file for MongoDB**:
   - Run:
     ```bash
     echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
     ```
   
3. **Reload local package database**:
   - Run:
     ```bash
     sudo apt-get update
     ```
   
4. **Install MongoDB packages**:
   - Run:
     ```bash
     sudo apt-get install -y mongodb-org
     ```
   
5. **Start MongoDB**:
   - Run:
     ```bash
     sudo systemctl start mongod
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

## CRUD Operations in MongoDB Compass

### Create
1. **Create a Database**:
   - Click on the `+` icon next to "My Cluster".
   - Enter a database name and collection name, then click "Create Database".

2. **Insert a Document**:
   - Select your database and collection.
   - Click on "Insert Document".
   - Add fields and values in the JSON document editor, then click "Insert".

### Read
1. **View Documents**:
   - Select your database and collection.
   - Documents will be displayed in the main window.

2. **Filter Documents**:
   - Use the "Filter" box to query documents. For example, to find documents where `name` is "John", enter:
     ```json
     { "name": "John" }
     ```

### Update
1. **Update a Document**:
   - Select the document you want to update.
   - Click on the pencil icon to edit the document.
   - Modify the fields and values, then click "Update".

2. **Bulk Update**:
   - Use the "Update Many" option to update multiple documents at once by specifying a filter and update criteria.

### Delete
1. **Delete a Document**:
   - Select the document you want to delete.
   - Click on the trash can icon to delete the document.

2. **Delete Multiple Documents**:
   - Use the "Delete Many" option to delete documents that match a specific filter.

## Additional Resources
- [MongoDB Documentation](https://docs.mongodb.com/)
- [MongoDB Compass Documentation](https://docs.mongodb.com/compass/current/)
- [MongoDB University](https://university.mongodb.com/)

