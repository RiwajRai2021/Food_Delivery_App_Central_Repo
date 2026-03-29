# Food_Delivery_App_Central_Repo


https://github.com/RiwajRai2021/Order_Repository.git

https://github.com/RiwajRai2021/RestaurantListing_Repository.git

https://github.com/RiwajRai2021/UserInfo_Repository.git

https://github.com/RiwajRai2021/Eureka_FD.git

https://github.com/RiwajRai2021/Food-Catalogue.git

https://github.com/RiwajRai2021/Food-Delivery-App-FE.git

<br><br>

<h1>Food Delivery App</h1>
<h3>Build Status: Deployment Ready</h3>

The Food Delivery App is a full‑stack platform that allows users to browse restaurants, explore menus, add items to cart, and place orders. The system includes secure authentication for both customers and admins, with admins able to manage restaurant listings and menu data. The application is containerized with Docker, automated with Jenkins CI/CD, and deployed on AWS for scalable cloud hosting.

**Scope: Solo project – Designed and developed full frontend and backend**

🎥 Demo Video
https://drive.google.com/file/d/132dC2QZUI6BV5VM92i99i5hwf-ZC0jFS/view?usp=sharing

![App Screenshot](https://github.com/RiwajRai2021/Food_Delivery_App_Central_Repo/blob/main/Screenshot%202026-03-26%20004002.png)
<br><br>

📑 Table of Contents

- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Data Flow Diagram](#data-flow-diagram)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Clone the Repository](#clone-the-repository)
  - [Set Up Environment Variables](#set-up-environment-variables)
- [Environment Variables Setup](#environment-variables-setup)
- [Contributing](#contributing)
- [License](#license)



# 🚀 <b>Quick Start Guide</b>   
Get the Food Delivery App running locally in just a few minutes! <br>

<b>Prerequisites</b><br>
Java 17+  
Node.js & Angular CLI  
MySQL  
Git  
<br>
# 📥 <b>Clone All Repositories</b><br>
git clone https://github.com/RiwajRai2021/Food_Delivery_App_Central_Repo.git<br>
git clone https://github.com/RiwajRai2021/Order_Repository.git<br>
git clone https://github.com/RiwajRai2021/RestaurantListing_Repository.git<br>
git clone https://github.com/RiwajRai2021/UserInfo_Repository.git<br>
git clone https://github.com/RiwajRai2021/Eureka_FD.git<br>
git clone https://github.com/RiwajRai2021/Food-Catalogue.git<br>
git clone https://github.com/RiwajRai2021/Food-Delivery-App-FE.git<br>

# 🌱<b> Set up Environment Variables</b><br>
<b>User Info Service</b><br>
cp UserInfo_Repository/.env.example UserInfo_Repository/.env

<b>Order Service</b><br>
cp Order_Repository/.env.example Order_Repository/.env

<b>Restaurant Listing Service</b><br>
cp RestaurantListing_Repository/.env.example RestaurantListing_Repository/.env

<b>Food Catalogue Service</b><br>
cp Food-Catalogue/.env.example Food-Catalogue/.env

<b>Eureka Server (if applicable)</b><br>
cp Eureka_FD/.env.example Eureka_FD/.env

<b>Frontend (if using .env)</b><br>
cp Food-Delivery-App-FE/.env.example Food-Delivery-App-FE/.env

# 🌐<b>Access the application</b><br>
<b>Frontend</b>: http://localhost:4200<br>
<b>Eureka Dashboard</b>:http://localhost:8761<br>
<b>User Info Service</b>:http://localhost:9093<br>
<b>Order Service</b>: http://localhost:9094<br>
<b>Restaurant Service</b>:http://localhost:9091<br>
<b>Food Catalogue Service</b>:http://localhost:9092
<br>
## Tech Stack

<b>Frontend</b>:
Angular,
TypeScript,
HTML/CSS

<b>Backend Microservices</b>:
Java,
Spring Boot,
Spring Web,
Spring Data JPA,
Spring Cloud Netflix Eureka,

<b>Architecture</b>:
Microservices Architecture,
Service Discovery (Eureka Server),
REST API Communication

<b>Database</b>:
MySQL,
MongoDB

<b>Containerization</b>:
Docker,
Docker Images for each microservice

<b>CI/CD</b>:
Jenkins (Build and Deployment Automation)

<b>Cloud Infrastructure</b>:
AWS EC2 (Compute),
AWS RDS (MySQL Database)

<b>Build Tools</b>:
Maven,
Node.js / npm

<b>Other Tools</b>:
Postman (API testing),
Git & GitHub (version control)
<br>

## 🏗️ Project Architecture

![Architecture Diagram](https://github.com/RiwajRai2021/Food_Delivery_App_Central_Repo/blob/main/FoodDeliveryApp_Project_Architecture.png)

<br>
⭐ <h2><b>Project Data‑Flow</b></h2>
1. <b>User and Admin Login</b>
The frontend sends a login request with email and password. Spring Security authenticates the credentials and returns a JWT token. Users and admins receive different permissions: users can browse and order food, while admins can add and manage restaurants.

2. <b>Restaurant Management</b> (Admin Only)
When an admin adds a restaurant, the frontend sends a secured POST request to the Restaurant Service. Spring Security verifies the admin role, and the service stores the restaurant details in its database.

3. <b>Browsing Restaurants and Menu Items</b>
Customers browse available restaurants and food items through the frontend. The frontend makes synchronous GET requests to the Restaurant Service and Food Catalogue Service, which return the required data from their respective databases.

4. <b>Placing an Order</b>
When a customer places an order, the frontend sends a POST request to the Order Service with the selected items, restaurant information, and total price. The JWT token is included for authentication.

5. <b>Fetching User Details</b>
The Order Service calls the User Service to retrieve the customer’s profile information (first name, last name, email). This ensures the order record is complete and accurate.

6. <b>Storing the Order</b>
The Order Service saves the order in its database with all relevant details, including items, user information, restaurant, total price, timestamp, and an initial status of “Placed.”

7. <b>Returning Order Confirmation</b>
The Order Service responds to the frontend with the order ID, status, and summary. The frontend displays a confirmation message to the customer.

⭐ <h2><b>Cloud Deployment Flow</h2></b>
8. <b>Code Push and CI Pipeline</b>
When code is pushed to GitHub, a webhook triggers Jenkins. Jenkins pulls the latest code, runs the Maven build, executes tests, builds a Docker image, and pushes it to Docker Hub or AWS ECR.

9. <b>Deployment to AWS</b>
You manually deploy the application to AWS. EC2 instances host your microservices, and RDS stores your relational data. Jenkins runs on its own EC2 instance, and security groups and IAM roles control access across the environment.

10. <b>Testing on the Cloud</b>
Once deployed, you test the application using the EC2 public IP or load balancer. You verify login, admin features, restaurant browsing, and order placement. You also confirm that order and restaurant data are correctly stored in RDS.












