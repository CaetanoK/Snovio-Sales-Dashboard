# Jupyter Notebook: Pipedrive Data Processing

This Jupyter Notebook is designed to process and analyze data from a Pipedrive API and perform various database operations. The code is divided into multiple sections that outline different stages of the data processing pipeline, including database setup, data retrieval, and data manipulation. Below are the main sections of the notebook explained in detail:

## 1. Getting Started

- **Importing Packages**: Various libraries such as `requests`, `json`, `pandas`, `sqlite3`, and others are imported to enable data handling and database connections.

- **Database Connections**: Connects to a MySQL database using `pymysql` for data storage and processing.

- **Pipedrive API Setup**: Sets up the base URL and API token to make API requests to the Pipedrive API.

## 2. Preparing Database

- **Creating Tables**: Defines a function to create tables in the MySQL database based on a list of table information.

- **Database Table Setup**: Specifies table information for different tables such as `Deal_Stage`, `User`, `Stage`, and more. The function is called to create the tables in the database.

- **Commit Changes**: Commits changes to the database to save the table creation.

## 3. Data Capture - Building Fact Tables

- **Creating Deal Table**: Defines a function to create a `Deal` table and a function to insert data into the table.

- **Retrieving and Inserting Data**: Retrieves data from the Pipedrive API and inserts it into the `Deal` table, handling duplicate keys appropriately.

- **Timestamp Handling**: Retrieves the last update timestamp from the `Deal` table to use as a reference for data retrieval.

## 4. Data Capture - Enriching Dimension Tables

- **Truncating Tables**: Truncates `User`, `Scheduled`, and `max_update_time` tables to clear existing data.

- **Inserting Native and Custom Data**: Retrieves data from the Pipedrive API and inserts it into various tables such as `User`, `Stage`, `Pipeline`, and others.

- **Mapping Parameters and Tables**: Uses dictionaries to map parameters from the API to the respective tables.

## 5. Organizing the Database

- **Deal Filtered Table**: Creates a `deal_filtered` table from the `Deal` table and performs data transformations and updates on columns.

- **SQL Commands**: Runs various SQL commands to organize and clean data in the `deal_filtered` table.

## 6. Further Adaptations and Customizations

- **Adapting User and Deal Filtered**: Runs additional SQL commands to adapt `User` and `deal_filtered` tables based on specific conditions.

## Conclusion

The notebook provides a comprehensive pipeline for processing Pipedrive data, handling data retrieval, storage, and manipulation within a MySQL database. By dividing the code into distinct sections, the notebook ensures organized data handling and facilitates easier maintenance and updates.
