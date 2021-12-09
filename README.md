# MovieStar
    - This project was developed with PHP in a course in Udemy for practice.
    - If you want to test it's necessary create the database, you can change 
    the configs for your favorite database in the "db.php".
## DataBase(to create tables if necessary)
    - CREATE DATABASE moviestar;
    - CREATE TABLE users(
        id INT(11) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(100),
        lastname VARCHAR(200),
        password VARCHAR(200),
        image VARCHAR(200),
        token VARCHAR(200),
        bio TEXT
    );
    - CREATE TABLE movies(
        id INT(11) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
        title VARCHAR(100),
        description TEXT,
        image VARCHAR(200),
        trailer VARCHAR(150),
        category VARCHAR(50),
        length VARCHAR(50),
        users_id INT(11) UNSIGNED,
        FOREIGN KEY (users_id) REFERENCES users(id)
    );
    - CREATE TABLE reviews(
        id INT(11) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
        rating INT,
        review TEXT,
        users_id INT(11) UNSIGNED,
        movies_id INT(11) UNSIGNED,
        FOREIGN KEY (users_id) REFERENCES users(id),
        FOREIGN KEY (movies_id) REFERENCES movies(id)
    );