
Project Overview

The Houston Covid Database is a structured SQL database designed to assist Houston residents in managing and accessing COVID-19 vaccination and testing resources. The database consolidates essential information regarding testing sites, vaccination centers, hospitals, clinics, pharmacies, and relevant organizations, providing a comprehensive, centralized source for users. This resource aids the public by providing data on availability, locations, and services, and includes functionalities for users to schedule appointments, search for nearby facilities, and access general COVID-19 vaccine information.

Mission Statement

The primary mission of this database is to collect, organize, and maintain COVID-19 resources and support information for Houston residents, aiding them in accessing essential healthcare services related to the pandemic.

Features and Functionalities

Database Components

The database encompasses the following entities, each with capabilities for creation, updating, and deletion of records:

Testing Sites: Data on COVID-19 testing locations, including names, addresses, phone numbers, and appointment availability.

Hospitals: Information on participating hospitals providing COVID-19 care.

Vaccination Sites: Details of vaccination centers with scheduling and availability information.

Pharmacies: Information on participating pharmacies, including addresses and contact details.

Clinics and Private Practices: Database for clinics providing COVID-19 care.

Insurance Providers: Database of insurance providers supporting COVID-19 services.

Vaccine Companies: Details on vaccine manufacturers supplying COVID-19 vaccines.

Counties and Cities: Geographic information to enable localized searches.

Users: User data for patients seeking COVID-19 services.

Core Functionalities

The project supports several core features:

Database Management:

Record creation, updates, and deletion for each entity (hospitals, clinics, testing sites, etc.).

User and administrative data management for facilitating personalized interactions.

Search Capabilities:

Users can perform searches by county, city, and entity (e.g., finding all pharmacies in Houston or testing sites in a specific county).
Admins can generate reports on COVID-19 resources by category.

Status Tracking:

The system tracks the operational status of testing and vaccination sites, vaccine companies, and county healthcare resources.

Report Generation:

Capabilities to report the number of available resources, such as the number of active vaccination sites or clinics by county.
Normalization and Integrity:

The database follows a rigorous normalization process up to BCNF to maintain data integrity and avoid redundancy.
Technical Specifications
Database: SQL-based relational model with strict normalization

Tables:
Hospitals, Testing Sites, Vaccination Sites, Pharmacies, Clinics, Users, Insurance Providers, Counties, Cities, and Vaccine Companies.

Normalization:

Database design follows 1NF, 2NF, 3NF, and BCNF principles to ensure optimized performance and data integrity.

SQL Queries
Below are a few sample SQL statements used within the project:

Add a Hospital:

sql
Copy code
INSERT INTO Hospitals (Hospital_name, Address, phone_no, City_id, County_id)
VALUES ('Houston Methodist', '6565 Fannin St', '7137903311', 1, 1);
Search for Pharmacies in Houston:

SELECT DISTINCT Pharmacy_name, City_name
FROM Pharmacies, Cities
WHERE City_name = 'Houston' AND Pharmacies.Pharmacy_id = Cities.City_id;
Count All Vaccination Sites:

SELECT COUNT(Vsite_name) FROM VacSites;
Entity-Relationship Diagram
[Include an ER Diagram image here if available]

Normalization Steps
The database has undergone the following normalization steps to ensure data efficiency and consistency:

1NF: Ensures atomic values in each cell.

2NF: No partial dependency on any candidate key.

3NF: Elimination of transitive dependencies.

BCNF: No attributes are derivable from others.

Usage

This project is suited for administrators of healthcare databases, public health officials, and developers focusing on healthcare data solutions. Below is the recommended procedure for utilizing the database:

Setup: Run the SQL scripts provided in the project to initialize the database tables.

Data Entry: Populate tables with initial data for hospitals, pharmacies, clinics, etc.

Perform Queries: Use provided SQL queries or customize them for specific reporting or data retrieval needs.

Maintenance: Keep the database up-to-date with the latest COVID-19 resource information by adding, updating, or removing entries as necessary.

Conclusion

The Houston Covid Database provides a robust, organized solution for managing and accessing COVID-19 healthcare resources in Houston. By centralizing information on COVID-19 services, this database empowers users to make informed decisions and ensures that healthcare providers can efficiently manage their resources.
