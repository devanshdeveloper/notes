

# PHP Exam Answers Set C

Q1. How to install XAMPP/WAMP?

1. **Introduction**
   - XAMPP/WAMP are popular local development environments for PHP web development
   - They provide an integrated package of Apache, MySQL, PHP, and other essential tools

2. **Installation Steps**
   - Download XAMPP/WAMP installer from official website
   - Run the installer with administrator privileges
   - Select components to install (Apache, MySQL, PHP, phpMyAdmin)
   - Choose installation directory
   - Complete installation and start services

3. **Post-Installation Setup**
   - Launch XAMPP/WAMP Control Panel
   - Start Apache and MySQL services
   - Verify installation by accessing:
     * http://localhost - Apache welcome page
     * http://localhost/phpmyadmin - Database management

4. **References**
   - https://www.apachefriends.org (XAMPP)
   - https://www.wampserver.com (WAMP)

Q2. Explain about PHP I/O controls.

1. **Introduction**
   - PHP I/O controls handle input/output operations
   - Essential for file handling and user interaction

2. **Main I/O Functions**
   - File Operations:
     ```php
     $file = fopen("test.txt", "r"); // Open file
     $content = fread($file, filesize("test.txt")); // Read file
     fwrite($file, "Hello World"); // Write to file
     fclose($file); // Close file
     ```
   - Standard I/O:
     ```php
     echo "Output text"; // Output
     print("Another output"); // Output
     $input = readline("Enter value: "); // Input (CLI)
     ```

3. **Error Handling**
   - Use try-catch blocks for error handling
   - Check file existence before operations

4. **References**
   - PHP Manual: https://www.php.net/manual/en/ref.filesystem.php

Q3. Explain the while-loop condition with an example.

1. **Introduction**
   - While loop executes a block of code as long as a condition is true
   - Useful for repetitive tasks with unknown iterations

2. **Syntax and Example**
   ```php
   // Count from 1 to 5
   $counter = 1;
   while ($counter <= 5) {
       echo "Count: $counter\n";
       $counter++;
   }

   // Reading file contents
   $file = fopen("data.txt", "r");
   while (!feof($file)) {
       echo fgets($file);
   }
   fclose($file);
   ```

3. **Key Points**
   - Condition checked before each iteration
   - Loop continues until condition becomes false
   - Must include a way to eventually break the loop

4. **References**
   - PHP Manual: https://www.php.net/manual/en/control-structures.while.php

Q4. What is variable scope? Explain example.

1. **Introduction**
   - Variable scope defines where a variable can be accessed
   - PHP has local, global, and static variable scopes

2. **Types of Scope**
   ```php
   $globalVar = "I'm global"; // Global scope

   function testScope() {
       $localVar = "I'm local"; // Local scope
       global $globalVar; // Access global variable
       static $counter = 0; // Static variable
       $counter++;
       
       echo $globalVar; // Accessible
       echo $localVar; // Only accessible within function
       echo $counter; // Maintains value between calls
   }
   ```

3. **Key Concepts**
   - Global variables accessible everywhere using global keyword
   - Local variables only accessible within their function
   - Static variables maintain value between function calls

4. **References**
   - PHP Manual: https://www.php.net/manual/en/language.variables.scope.php

Q5. Explain $_POST with an example.

1. **Introduction**
   - $_POST is a PHP superglobal for handling POST request data
   - Commonly used for form submissions

2. **Example Implementation**
   ```php
   <!-- HTML Form -->
   <form method="POST" action="process.php">
       <input type="text" name="username">
       <input type="password" name="password">
       <input type="submit" value="Login">
   </form>

   <!-- process.php -->
   <?php
   if ($_SERVER["REQUEST_METHOD"] == "POST") {
       $username = $_POST["username"];
       $password = $_POST["password"];
       
       // Process form data
       if (!empty($username) && !empty($password)) {
           echo "Login attempt for user: " . htmlspecialchars($username);
       }
   }
   ?>
   ```

3. **Security Considerations**
   - Always validate and sanitize POST data
   - Use htmlspecialchars() to prevent XSS
   - Never store passwords in plain text

4. **References**
   - PHP Manual: https://www.php.net/manual/en/reserved.variables.post.php

Q6. Write short notes on the hash function.

1. **Introduction**
   - Hash functions convert data into fixed-size strings
   - Essential for password security and data integrity

2. **Common Hash Functions**
   ```php
   // MD5 (not recommended for passwords)
   $md5Hash = md5("text"); 

   // SHA-256
   $sha256Hash = hash("sha256", "text");

   // Password Hashing (recommended)
   $passwordHash = password_hash("mypassword", PASSWORD_DEFAULT);
   
   // Verify Password
   $isValid = password_verify("mypassword", $passwordHash);
   ```

3. **Best Practices**
   - Use password_hash() for password storage
   - Never store plain text passwords
   - Use strong algorithms (SHA-256, bcrypt)
   - Add salt for additional security

4. **References**
   - PHP Manual: https://www.php.net/manual/en/function.password-hash.php

Q7. What is RDBMS? Explain how to DELETE Table.

1. **Introduction**
   - RDBMS (Relational Database Management System) is a database system that stores and manages data in tables
   - Tables are related to each other through common fields (keys)
   - Popular RDBMS include MySQL, PostgreSQL, Oracle, and SQL Server

2. **Key Concepts**
   - Tables (Relations)
   - Records (Rows)
   - Fields (Columns)
   - Primary Keys
   - Foreign Keys
   - SQL (Structured Query Language)

3. **Deleting Tables**
   ```sql
   -- Basic DELETE table syntax
   DROP TABLE table_name;

   -- Check if table exists before deleting
   DROP TABLE IF EXISTS table_name;

   -- Delete multiple tables
   DROP TABLE table1, table2, table3;

   -- Delete table and related references
   DROP TABLE table_name CASCADE;
   ```

4. **References**
   - MySQL Manual: https://dev.mysql.com/doc/refman/8.0/en/drop-table.html

Q8. What are arrays? Explain arrays with an example program.

1. **Introduction**
   - Arrays are data structures that store multiple values in a single variable
   - PHP supports both indexed and associative arrays
   - Arrays can store different types of data

2. **Types and Examples**
   ```php
   // Indexed Array
   $fruits = array("Apple", "Banana", "Orange");
   // or
   $fruits = ["Apple", "Banana", "Orange"];

   // Associative Array
   $person = array(
       "name" => "John",
       "age" => 25,
       "city" => "New York"
   );

   // Multidimensional Array
   $students = array(
       array("John", "Math", 85),
       array("Jane", "Science", 92),
       array("Bob", "English", 78)
   );

   // Array Operations
   echo $fruits[0];  // Output: Apple
   echo $person["name"];  // Output: John
   echo $students[1][2];  // Output: 92

   // Loop through array
   foreach ($fruits as $fruit) {
       echo $fruit . "\n";
   }
   ```

3. **Array Functions**
   - count() - Count elements
   - array_push() - Add element
   - array_pop() - Remove last element
   - sort() - Sort indexed arrays
   - asort() - Sort associative arrays by values
   - ksort() - Sort associative arrays by keys

4. **References**
   - PHP Manual: https://www.php.net/manual/en/language.types.array.php

Q9. How to search and replace the strings? Explain with example

1. **Introduction**
   - PHP provides various functions for string manipulation
   - Common operations include search, replace, and pattern matching

2. **String Functions**
   ```php
   // Basic string replacement
   $text = "Hello World";
   $newText = str_replace("World", "PHP", $text);
   echo $newText;  // Output: Hello PHP

   // Case-insensitive replacement
   $text = "HELLO World";
   $newText = str_ireplace("hello", "Hi", $text);
   echo $newText;  // Output: Hi World

   // Multiple replacements
   $search = array("Hello", "World");
   $replace = array("Hi", "PHP");
   $text = "Hello World";
   $newText = str_replace($search, $replace, $text);
   echo $newText;  // Output: Hi PHP

   // Regular Expression replacement
   $text = "Contact us at info@example.com";
   $pattern = "/([a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,})/";
   $replacement = "<a href=\"mailto:$1\">$1</a>";
   $newText = preg_replace($pattern, $replacement, $text);
   echo $newText;  // Output: Contact us at <a href="mailto:info@example.com">info@example.com</a>
   ```

3. **Key Functions**
   - str_replace() - Replace text
   - str_ireplace() - Case-insensitive replace
   - preg_replace() - Regular expression replace
   - strpos() - Find position of string
   - stripos() - Case-insensitive position search

4. **References**
   - PHP Manual: https://www.php.net/manual/en/ref.strings.php

Q10. How to connect the MySQL Database?

1. **Introduction**
   - PHP offers multiple ways to connect to MySQL databases
   - Common approaches: MySQLi (procedural/OOP) and PDO

2. **Connection Methods**
   ```php
   // MySQLi Object-Oriented
   $conn = new mysqli("localhost", "username", "password", "database");
   if ($conn->connect_error) {
       die("Connection failed: " . $conn->connect_error);
   }
   echo "Connected successfully";

   // MySQLi Procedural
   $conn = mysqli_connect("localhost", "username", "password", "database");
   if (!$conn) {
       die("Connection failed: " . mysqli_connect_error());
   }
   echo "Connected successfully";

   // PDO
   try {
       $conn = new PDO("mysql:host=localhost;dbname=database", "username", "password");
       $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
       echo "Connected successfully";
   } catch(PDOException $e) {
       echo "Connection failed: " . $e->getMessage();
   }
   ```

3. **Best Practices**
   - Use environment variables for credentials
   - Implement error handling
   - Close connections when done
   - Use prepared statements for queries
   - Consider connection pooling for performance

4. **References**
   - PHP Manual: https://www.php.net/manual/en/book.mysqli.php
   - PHP Manual: https://www.php.net/manual/en/book.pdo.php