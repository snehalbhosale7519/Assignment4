# Assignment4
### Project Overview

- This project demonstrates how to:
- Connect a Java application (built in NetBeans IDE) to a MySQL database using JDBC.
- Design a simple homepage using JFrame with navigation buttons and labels.


### ⚙️ Requirements

- NetBeans IDE (latest version recommended)
- Java Development Kit (JDK 8 or higher)
- MySQL Server (e.g., XAMPP, WAMP, or standalone installation)
- MySQL Connector/J (JDBC driver)


### Setup Instructions
1. Install MySQL JDBC Driver

-Download MySQL Connector/J from the official website.
-In NetBeans, right-click Libraries > Add JAR/Folder > select the .jar file.

2. Database Connection

Create a class DatabaseConnection.java with the following code:
- import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class DatabaseConnection {
    private static final String URL = "jdbc:mysql://localhost:3306/your_database_name";
    private static final String USER = "your_mysql_username";
    private static final String PASSWORD = "your_mysql_password";

    public static Connection getConnection() {
        Connection connection = null;
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            connection = DriverManager.getConnection(URL, USER, PASSWORD);
            System.out.println("Connected to MySQL database!");
        } catch (ClassNotFoundException | SQLException e) {
            System.err.println("Connection error: " + e.getMessage());
        }
        return connection;
    }

    public static void main(String[] args) {
        getConnection();
    }
}
- Note: Replace your_database_name, your_mysql_username, and your_mysql_password with your actual credentials.
 
3. Homepage Design

-Create a JFrame Form named Homepage.

Add:

A title label: “Welcome to the Homepage”

A greeting label: “Hello, User!”

Buttons: View Profile, Settings, Logout

Use GroupLayout for proper alignment.

4. Run & Test

Run DatabaseConnection.java → Check if connection works.

Run Homepage.java → Verify layout & button functionality.
