Required Software and Libraries:
1.Before running this project, make sure the following software and libraries are installed on your system:

Java Development Kit (JDK):

You need JDK 8 or later to run this project.
If you don't have Java installed, download it from Oracle JDK or OpenJDK.
Make sure to download JDK 8 if you want JavaFX to work without extra configuration. For later versions of Java(after 11) you'll                                  need to separately install openJFX.

2.IDE (Integrated Development Environment):

You need an IDE to open and run the project. I recommend using:
IntelliJ IDEA (Community version).
Eclipse (Free).
NetBeans (Free).
We would prefer IntelliJ IDEA because that's what we used.

3.Database Software:

The project uses a MySQL database to store user data, meals, and workouts.
Download and install MySQL.

4.Libraries:

The project uses JavaFX for the graphical user interface (GUI).
For Java versions 11+, you’ll need to install OpenJFX to use JavaFX components like buttons, lists, and charts.
If using Maven, all dependencies will be automatically handled (more on that later).





Steps to run the project:

STEP 1:
Create the Database: You need to set up a database to store the user’s information, meals, and workouts.

Open MySQL Workbench or your preferred database tool.
Create a new database called nutrition_tracker

CREATE DATABASE nutrition_tracker;
USE nutrition_tracker;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255),
    password VARCHAR(255),
    name VARCHAR(255),
    age INT,
    weight DOUBLE,
    height DOUBLE,
    goal VARCHAR(255)
);

CREATE TABLE meals (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255),
    mealName VARCHAR(255),
    date DATE,
    calories DOUBLE,
    FOREIGN KEY (username) REFERENCES users(username)
);

CREATE TABLE workouts (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255),
    workoutName VARCHAR(255),
    date DATE,
    duration DOUBLE,
    FOREIGN KEY (username) REFERENCES users(username)
);


STEP 2:
Add Required Libraries:

If you're using an IDE like IntelliJ IDEA or Eclipse, you need to add the following libraries to the project:
JDBC Driver: If using MySQL, download the MySQL Connector/J (mysql-connector-java JAR) and add it to the libraries.
JavaFX: If using Java 11 or later, download and configure OpenJFX (JavaFX) from here.
Maven Setup (Optional):

If you’re using Maven, dependencies will be handled automatically. Just make sure you have the pom.xml file in the project with the required dependencies.


STEP 3:
Build and Run the Project
In IntelliJ IDEA:

Open the project folder in IntelliJ.
Check that all the libraries (JDBC, JavaFX, etc.) are added in the Project Structure under Libraries.
Click Build > Build Project to compile the project.
Once the project is built, click the green Run button (or press Shift + F10) to run the project.

Run the Application:

When you run the project, the Login Page will appear first.
You can register a new user or log in with an existing user.
Once logged in, you’ll be able to:
View meal history and workout history.
Calculate total calories and workout duration.
View graphical charts of calories and workout times.
