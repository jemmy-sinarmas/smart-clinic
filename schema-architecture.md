# Smart Clinic Management System – Architecture Design

## 1. Architecture Summary
The Smart Clinic Management System is designed using a **three-tier architecture** consisting of the Presentation Layer, Application Layer, and Data Layer. The frontend is built with HTML, CSS, JavaScript, and Thymeleaf templates served by Spring Boot. The backend is developed using **Spring Boot**, following the MVC (Model-View-Controller) pattern and exposing RESTful APIs for interaction. It uses **MySQL** to store structured relational data like users, appointments, and clinics, and **MongoDB** to store flexible unstructured data like medical prescriptions. The application ensures scalability, security, and maintainability, with the backend containerized using Docker and CI workflows implemented for automated testing and deployment.

## 2. Request/Response Flow

1. **User Interaction (Frontend)**
   - A user (Admin, Doctor, or Patient) accesses the web portal via browser.
   - The user can interact with HTML pages rendered by Thymeleaf or call REST APIs using JavaScript/AJAX for dynamic content.

2. **HTTP Request to Backend**
   - The request is sent to the Spring Boot application.
   - Based on the endpoint, the request is handled by either a Thymeleaf controller (for page rendering) or a REST controller (for API response).

3. **Controller Layer (Spring Boot)**
   - MVC Controllers: Handle web page requests, prepare model data, and return Thymeleaf templates.
   - REST Controllers: Handle API requests (CRUD for patients, doctors, appointments, prescriptions).

4. **Service Layer**
   - Business logic is processed here, including validation, scheduling, user authentication, and role-based authorization.
   - The service layer communicates with the repositories to access the databases.

5. **Data Access Layer**
   - **MySQL Database (via Spring Data JPA):**
     - Stores structured data: Users (Admin, Doctor, Patient), Appointments, Medical Histories, Clinic details.
   - **MongoDB Database (via Spring Data MongoDB):**
     - Stores unstructured or semi-structured data: Medical Prescriptions, Notes, Attachments.

6. **Database Operations**
   - CRUD operations are performed using JPA for MySQL and MongoTemplate or MongoRepository for MongoDB.
   
7. **Response to Frontend**
   - For page-based requests: Thymeleaf templates are rendered and returned.
   - For API requests: JSON responses are returned.

8. **Frontend Update**
   - The browser updates the page view with the returned data or renders the new page.
   - The process is completed with seamless user interaction.

## Technologies Used
- **Frontend:** HTML, CSS, JavaScript, Thymeleaf
- **Backend:** Java, Spring Boot, Spring MVC, REST APIs
- **Databases:** MySQL (relational), MongoDB (NoSQL)
- **Deployment:** Docker, CI/CD pipelines
- **Version Control:** GitHub

---

## ✅ Submission Checklist:
- [x] Created `schema-architecture.md`
- [x] Described the architecture in your own words
- [x] Listed step-by-step request/response flow
- [x] Committed with message: `"Added architecture design for Smart Clinic app"`
- [x] Pushed to GitHub repository `java-database-capstone`
