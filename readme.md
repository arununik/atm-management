sql code
    Create Database atm;

    
    CREATE TABLE User ( 
        accno INT PRIMARY KEY,
        name VARCHAR(255),
        ifsc VARCHAR(255),
        address VARCHAR(255),
        phoneno VARCHAR(255),
        age INT
    );
    
    CREATE TABLE Card (
        cardno INT PRIMARY KEY,
        accno INT,
        acctype VARCHAR(255),
        name_card VARCHAR(255),
        pin VARCHAR(255),
        bankname VARCHAR(255),
        expiredate DATE,
        cvv INT,
        balance DECIMAL(10, 2),
        FOREIGN KEY (accno) REFERENCES User(accno)
    );  
    
    CREATE TABLE Transaction (
        transid INT PRIMARY KEY AUTO_INCREMENT,
        cardno INT,
        transtype VARCHAR(255),
        amt DECIMAL(10, 2),
        date DATE,
        time TIME,
        FOREIGN KEY (cardno) REFERENCES Card(cardno)
    );
    ```
