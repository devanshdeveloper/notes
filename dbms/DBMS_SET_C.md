# Database Management System - Set C

Q1. Discuss Conventional file system compared to Modern DBMS.

1. **Introduction**
   - Conventional file systems vs database management systems
   - Evolution from file-based storage to structured databases

2. **Main Content**
   - **Conventional File System:**
     * Data redundancy and inconsistency
     * Limited data sharing
     * No crash recovery mechanism
     * Difficulty in concurrent access
     * Example: Text files storing student records

   - **Modern DBMS:**
     * Centralized data management
     * ACID properties (Atomicity, Consistency, Isolation, Durability)
     * Advanced query processing
     * Example: MySQL database with normalized tables

   **Comparison Table:**
   ```
   | Aspect            | File System          | DBMS                 |
   |--------------------|----------------------|----------------------|
   | Data Redundancy    | High                 | Controlled           |
   | Concurrency Control| None                 | ACID Implemented     |
   | Security           | File-level           | Granular access      |
   | Data Relationship  | Manual maintenance   | Built-in constraints |
   ```

3. **Conclusion**
   - DBMS provides superior data management capabilities
   - Essential for complex data operations and enterprise applications

4. **References**
   - Database System Concepts by Silberschatz
   - www.guru99.com/file-system-vs-dbms.html

---

Q2. Discuss types of Attributes in E-R Diagram.

1. **Introduction**
   - Attributes define properties of entities in ER modeling
   - Critical for detailed database design

2. **Main Content**
   a) **Simple vs Composite**
   - Simple: Atomic values (e.g., Age)
   - Composite: Divisible components (e.g., Address → Street, City)

   b) **Single-Valued vs Multivalued**
   - Single: One value per entity (e.g., EmployeeID)
   - Multivalued: Multiple values (e.g., PhoneNumbers)

   c) **Derived Attributes**
   - Computed from other attributes
   - Example: Age derived from BirthDate

   d) **Key Attributes**
   - Uniquely identify entities
   - Example: StudentID in Student entity

3. **Conclusion**
   - Proper attribute classification ensures effective modeling
   - Fundamental to database normalization

4. **References**
   - Entity-Relationship Modeling Essentials
   - www.visual-paradigm.com/erd-tutorial

---

Q3. Overcome anomalies in Normalization & Explain Multivalued dependency.

1. **Introduction**
   - Normalization eliminates data anomalies
   - Multivalued dependency occurs in 4NF scenarios

2. **Main Content**
   - **Anomaly Solutions:**
     * Insertion: Proper foreign key constraints
     * Deletion: Cascade delete rules
     * Update: Atomic transactions

   - **Multivalued Dependency:**
     * Occurs when multiple independent multi-valued facts
     * Example: Employee → {Skills}, {Certifications}
     * Resolution using 4NF:
       ```sql
       CREATE TABLE EmployeeSkills (
           EmpID INT,
           Skill VARCHAR(50)
       );

       CREATE TABLE EmployeeCerts (
           EmpID INT,
           Certification VARCHAR(50)
       );
       ```

3. **Conclusion**
   - Proper normalization eliminates data inconsistencies
   - Higher normal forms handle complex dependencies

4. **References**
   - Database Normalization Guide
   - www.1keydata.com/database-normalization/multivalued-dependency.html

---

Q4. Explain SELECT command clauses with examples.

1. **Introduction**
   - SELECT retrieves data from database tables
   - Clauses refine query results

2. **Main Content**
   a) **WHERE Clause**
   ```sql
   SELECT * FROM Employees
   WHERE Department = 'IT';
   ```

   b) **GROUP BY Clause**
   ```sql
   SELECT Department, AVG(Salary)
   FROM Employees
   GROUP BY Department;
   ```

   c) **HAVING Clause**
   ```sql
   SELECT Department, COUNT(*)
   FROM Employees
   GROUP BY Department
   HAVING COUNT(*) > 10;
   ```

   d) **ORDER BY Clause**
   ```sql
   SELECT Name, Salary
   FROM Employees
   ORDER BY Salary DESC;
   ```

3. **Conclusion**
   - Clause combination enables powerful data queries
   - Essential for data analysis and reporting

4. **References**
   - SQL Complete Guide
   - www.w3schools.com/sql/sql_ref_select.asp

---

Q5. Explain Indexing and Hashing types.

1. **Introduction**
   - Indexing and hashing improve data retrieval
   - Different types serve specific optimization needs

2. **Main Content**
   - **Indexing Types:**
     * B-Tree: Balanced tree structure
     * Bitmap: For low-cardinality data
     * Covering: Includes all query fields

   - **Hashing Types:**
     * Static Hashing: Fixed hash function
     * Dynamic Hashing: Adjustable hash table
     * Extendible Hashing: Handles growing datasets

3. **Conclusion**
   - Proper indexing/hashing strategy crucial for performance
   - Choice depends on data characteristics

4. **References**
   - Database Performance Tuning
   - www.ibm.com/docs/en/db2/11.5?topic=indexes-types