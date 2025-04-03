# UNIT-I: BASICS OF PHP

## Introduction to PHP
PHP (Hypertext Preprocessor) is a server-side scripting language designed specifically for web development.

### Key Points
- Created by Rasmus Lerdorf in 1994
- Open-source language
- Embedded directly in HTML
- Executed on the server-side

## PHP Features

### Core Features
- Server-side scripting
- Command-line scripting
- Cross-platform compatibility
- Database support
- Error handling
- Security features

```mermaid
graph TD
    A[PHP Features] --> B[Server-side Scripting]
    A --> C[Database Integration]
    A --> D[Security Features]
    A --> E[Error Handling]
    A --> F[Cross-platform]
    B --> G[Dynamic Content]
    C --> H[MySQL Support]
    D --> I[Input Validation]
    E --> J[Debug Support]
    F --> K[OS Independence]
```

## XAMPP/WAMP Installation

### XAMPP Components
- Apache (Web Server)
- MySQL (Database)
- PHP (Scripting Language)
- phpMyAdmin (Database Management)
- Pearl

```mermaid
graph LR
    A[XAMPP] --> B[Apache]
    A --> C[MySQL]
    A --> D[PHP]
    A --> E[phpMyAdmin]
    A --> F[Pearl]
    B --> G[Web Server]
    C --> H[Database Server]
    D --> I[Script Processing]
    E --> J[DB Management]
```

## Benefits of PHP-MySQL

### Advantages
1. Cost-effective (Open Source)
2. Large Community Support
3. Cross-platform Compatibility
4. Easy Integration
5. Robust Security Features

## Server-Client Environment

```mermaid
sequenceDiagram
    participant Client
    participant WebServer
    participant PHP
    participant Database
    Client->>WebServer: HTTP Request
    WebServer->>PHP: Process PHP Script
    PHP->>Database: Query Data
    Database->>PHP: Return Data
    PHP->>WebServer: Generate HTML
    WebServer->>Client: HTTP Response
```

### Components
1. **Client Side**
   - Web Browser
   - HTML/CSS/JavaScript
   - User Interface

2. **Server Side**
   - Web Server (Apache)
   - PHP Interpreter
   - Database Server

## Web Server Installation & Configuration

### Apache Configuration Files
- **httpd.conf**: Main configuration file
- **php.ini**: PHP configuration
- **my.ini**: MySQL configuration

```mermaid
graph TD
    A[Configuration Files] --> B[httpd.conf]
    A --> C[php.ini]
    A --> D[my.ini]
    B --> E[Server Settings]
    B --> F[Directory Config]
    C --> G[PHP Settings]
    C --> H[Extensions]
    D --> I[MySQL Config]
    D --> J[Performance]
```

## Exam Focus Points

### Key Concepts to Remember
1. **PHP Basics**
   - Syntax and structure
   - Variables and data types
   - Control structures

2. **Server Architecture**
   - Request processing flow
   - Role of each component
   - Configuration importance

3. **Database Integration**
   - Connection methods
   - Basic operations
   - Security practices

### Practice Questions
1. What is PHP and why is it used in web development?
2. Explain the components of XAMPP/WAMP.
3. Describe the client-server architecture in web applications.
4. List the main configuration files and their purposes.
5. What are the benefits of using PHP with MySQL?