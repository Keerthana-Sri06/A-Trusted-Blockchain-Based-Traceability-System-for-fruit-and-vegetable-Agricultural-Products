# A-Trusted-Blockchain-Based-Traceability-System-for-fruit-and-vegetable-Agricultural-Products
Overview

This project implements a Trusted Blockchain-Based Traceability System for fruits and vegetables using Java, JSP, Servlets, and MySQL.
It ensures secure product tracking from farm to consumer, improving trust, transparency, and fraud prevention in the supply chain.

The system allows:

👨‍🌾 Farmers to add products.

🏬 Distributors/Retailers to trace product history.

🔒 Blockchain to secure transaction records.

🏗️ Project Structure
TraceabilitySystem/
├── src/
│   └── main/
│       ├── java/com/traceability/
│       │   ├── controllers/       # Servlets (Login, AddProduct, TraceProduct)
│       │   ├── models/            # User, Product classes
│       │   ├── dao/               # Database layer (DBConnection, DAO classes)
│       │   ├── blockchain/        # Blockchain, Block, Transaction logic
│       │   └── util/              # Utility functions
│       │
│       └── webapp/
│           ├── assets/            # CSS, JS, Images
│           ├── WEB-INF/           # web.xml, lib (JARs)
│           ├── login.jsp
│           ├── dashboard.jsp
│           ├── addProduct.jsp
│           └── traceProduct.jsp
│
├── README.md
└── pom.xml (if Maven)

💾 Database Setup (MySQL)

Run the following SQL script:

CREATE DATABASE traceability_db;

USE traceability_db;

-- User Table
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(100) NOT NULL,
    role ENUM('farmer','retailer','admin') NOT NULL
);

-- Product Table
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    origin VARCHAR(100) NOT NULL,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Blockchain Transactions
CREATE TABLE transactions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    product_id INT,
    details TEXT,
    hash VARCHAR(256),
    prev_hash VARCHAR(256),
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (product_id) REFERENCES products(id)
);

⚙️ Installation & Deployment
🔹 Prerequisites

JDK 8+

Apache Tomcat (9/10)

MySQL / XAMPP

Eclipse IDE (Dynamic Web Project)

🔹 Steps

Clone this repository:

git clone https://github.com/your-username/TraceabilitySystem.git


Import the project into Eclipse as a Dynamic Web Project.

Configure Tomcat server in Eclipse.

Add mysql-connector-java-x.x.jar in WEB-INF/lib.

Update DBConnection.java with your MySQL credentials.

Create the database using the SQL script above.

Run on Tomcat Server → Open in browser:

http://localhost:8080/TraceabilitySystem/login.jsp

🖥️ Features

✅ User Authentication (Farmer, Retailer, Admin)
✅ Add & Manage Agricultural Products
✅ Blockchain-secured Transaction Records
✅ Product Traceability (view full history)
✅ JSP + Servlet based MVC Architecture

📷 Screenshots

<img width="1084" height="557" alt="Screenshot 2025-08-15 091830" src="https://github.com/user-attachments/assets/26c3d319-df50-4dcb-a2ed-4fb90cae3fe0" />


🛠️ Technologies Used

Frontend: JSP, HTML, CSS, JavaScript

Backend: Java Servlets, JDBC

Database: MySQL

Server: Apache Tomcat

Blockchain Logic: Custom Java classes

🚀 Future Enhancements

🔐 Role-based Access Control with JWT

📱 Mobile App Integration

☁️ Cloud deployment (AWS/Azure)

🤖 AI/ML-based fraud detection

🤝 Contributing

Contributions are welcome! Please fork the repo and submit a pull request.

📜 License

This project is licensed under the MIT License – feel free to use and modify it.
