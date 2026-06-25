Recipe System API (Spring Boot + JWT)

A REST API built with Spring Boot, Spring Security, JWT authentication, and H2 in-memory database. The application supports user authentication and basic recipe management with role-based access control.

Features
Authentication
User registration
User login
JWT token generation
JWT token validation
Stateless authentication
Roles
USER: can create and view recipes
ADMIN: can delete and manage all recipes
Recipes
Create recipe
Get all recipes
Get recipe by id
Update recipe
Delete recipe
Technology Stack
Java 21
Spring Boot
Spring Security
JSON Web Token (JWT)
Spring Data JPA
H2 Database
Maven
Lombok
Project Structure
com.example.recipe_system
 ├── controller
 ├── service
 ├── service/implementation
 ├── repository
 ├── entity
 ├── security
 ├── dto
Authentication Flow
User registers using /auth/register
User logs in using /auth/login
Server returns a JWT token
Client sends token in request header:
Authorization: Bearer <token>
JWT filter validates the token
Access is granted based on user role
API Endpoints
Authentication
Register
POST /auth/register

Request:

{
  "username": "john",
  "email": "john@mail.com",
  "password": "1234"
}
Login
POST /auth/login

Request:

{
  "email": "john@mail.com",
  "password": "1234"
}

Response:

JWT token string
Recipes
Create Recipe (requires JWT)
POST /recipes

Header:

Authorization: Bearer <token>

Request:

{
  "title": "Pasta",
  "description": "Creamy pasta",
  "ingredients": "Pasta, cream, salt",
  "instructions": "Boil and mix"
}
Get All Recipes
GET /recipes
Get Recipe by ID
GET /recipes/{id}
Update Recipe
PUT /recipes/{id}
Delete Recipe
DELETE /recipes/{id}
H2 Database Console

Access:

http://localhost:8080/h2-console

Settings:

JDBC URL: jdbc:h2:mem:testdb
Username: sa
Password: (empty)
Postman Usage
Register a user
Login and copy token
Add header:
Authorization: Bearer <token>
Test recipe endpoints
Common Issues
401 Unauthorized: missing or invalid token
403 Forbidden: role or authorization issue
Application not starting: missing Spring beans or configuration issues
Future Improvements
Add PostgreSQL or MySQL support
Add Swagger/OpenAPI documentation
Add refresh token system
Add recipe categories and search

If you want next step, I can also help you:

fix your 403 completely
secure admin endpoints properly
or clean your project structure so it stops breaking during builds
