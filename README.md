Documentation for Database Normalization Code

5300 – Database Systems

Programming Project – 1 Documentation

Group:

1.	Sikindhar Reddy Gangidi
2.	Jagadish Pasupuleti
3.	Rohit Reddy Somu
4.	Abijeeth Reddy Gorla
5.	Praneeth Kumar Gantyada
6.	
Introduction:

The provided code offers a suite of functions that decompose a dataset into different normal forms, specifically 1NF, 2NF, 3NF, BCNF, 4NF, and 5NF. Each function reads data from a CSV file, checks if it meets the conditions of the respective normal form, and prints out SQL queries to create the normalized tables.

Code Structure:

1. Utility Functions: 

      `parse_fd(fd)`: This function is used to parse functional dependencies and split them into their left-hand side (LHS) and right-hand side (RHS) components.

2. Decomposition Functions:

•	`decompose_to_1NF()`: Checks if the table is in 1NF and, if not, normalizes it.

•	`decompose_to_2NF()`: Decomposes the table to 2NF by using the provided functional dependencies and table keys.

•	`decompose_to_3NF()`: Ensures that the table is in 3NF by removing any transitive dependencies based on functional dependencies.

•	`decompose_to_BCNF()`: Decomposes the table into BCNF. Here, the table structure is directly provided for normalization.

•	`decompose_to_4NF()`: Decomposes the table to 4NF by ensuring there are no multi-valued dependencies.

•	`decompose_to_5NF()`: Decomposes the table to 5NF or Project-Join Normal Form (PJNF) ensuring no join dependencies.

3. Main Flow:
    
•	In the `main()` function, the user is prompted to input functional dependencies and multi-valued dependencies.

•	The user is then prompted to specify the normal form they wish to decompose the table into. 

•	Based on the user’s choice, the respective decomposition function is called.

4. Checking & Creation Logic:

•	Each decomposing function checks if the table meets the conditions for its respective normal form.

•	If the conditions aren't met, the table is decomposed accordingly.

•	SQL `CREATE TABLE` queries reflecting the decomposed structure are printed out for each normalized table.

Methodology:

1. 1NF: Checks for atomicity. If any column contains comma-separated values (indicating non-atomic values), it's not in 1NF.

2. 2NF: Tables are created by examining functional dependencies. Any partial dependency (i.e., an attribute is functionally dependent on a part of the primary key) is removed.

3. 3NF: Transitive dependencies (i.e., an attribute is functionally dependent on another non-primary key attribute) are removed.

4. BCNF: For every non-trivial functional dependency X -> Y, X should be a super key. The code provides a direct schema for BCNF.

5. 4NF: Multi-valued dependencies are removed. For any dependency like X ->> Y, X should be a super key.

6. 5NF (PJNF): The code sets the table index based on the primary key and another attribute. It then creates separate tables for each combination of the primary key's values, ensuring there are no join dependencies.

 Usage:

Run the `main()` function, provide functional and multi-valued dependencies as prompted, and then choose the desired normal form. The code will output SQL queries for creating the normalized tables. 

Note:

•	The code assumes a CSV file path ("/content/DB_new_1.csv") as the source of the data, which should be replaced or parameterized as per actual usage.
•	The code doesn’t actually execute SQL queries but prints them out for user reference.

Conclusion:

This code is a comprehensive solution for database normalization up to 5NF. It is helpful for both database design and academic purposes, allowing users to understand the principles of normalization and see them in practice.
