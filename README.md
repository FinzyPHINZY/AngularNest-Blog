# AngularNest Blog

This is a blog application built using NestJS for the backend and Angular for the frontend. The backend utilizes TypeORM with PostgreSQL database and implements various CRUD operations for managing users and blog entries. The application also includes authentication with JWT, role-based API protection, pagination, real-time search, and image uploading functionality.

## Project Planning

The project was planned using Trello, a project management tool. Tasks, features, and progress were tracked using Trello boards.

## Technologies Used

- **NestJS**: Backend framework for building scalable and maintainable server-side applications.
- **Angular**: Frontend framework for building dynamic web applications.
- **TypeORM**: Object-Relational Mapping (ORM) library for TypeScript and JavaScript.
- **PostgreSQL**: Relational database management system used for data storage.
- **GitLab**: Version control system for managing the project's source code.
- **RxJS**: Library for reactive programming using Observables.
- **Docker**: Containerization platform used for easy deployment and management of the application.

## Features

- **CRUD Operations**: Users can perform various CRUD operations such as creating, reading, updating, and deleting blog entries and user profiles.
- **Authentication**: Implemented login endpoint with email and password authentication. Passwords are securely hashed before being stored in the database. JWT tokens are generated upon login.
- **Role-Based Access Control**: Certain endpoints are protected with JWT tokens, and access is restricted based on user roles. Custom guards with `@hasRole()` annotation and JWT Guard are used for authorization.
- **Pagination**: Paginated results for better performance and user experience.
- **Real-Time Search**: Users can filter blog entries by username in real-time and paginate the results.
- **Image Upload**: Support for uploading profile images and images for blog entries.
- **Guard for PUT Requests**: Added guard to verify that the user making a PUT request is the owner of the resource.
- **GitFlow Integration**: Utilized GitFlow workflow for managing feature development and release cycles.

## Instructions to Run the Project

### With Docker

1. Run the following command to start the application:
   ```
   docker-compose up
   ```
2. Visit `localhost:4200` in your browser to access the application.

### Without Docker

1. Add an environment file to the project by creating a `.env` file in the `api` folder. Add the following environment variables:

   - `DATABASE_URL`: URL for connecting to the PostgreSQL database.
   - `JWT_SECRET`: Secret key for generating JWT tokens.

2. Start the backend in dev mode after adding the `.env` file:

   ```
   cd api
   npm install
   npm run start:dev
   ```

3. Start the frontend in dev mode after adding the `.env` file:

   ```
   cd frontend
   npm install
   ng serve
   ```

## Tips & Tricks for Docker

- To remove all Docker images:

  ```
  docker rmi -f $(docker images -a -q)
  ```

- To remove all Docker containers:
  ```
  docker rm -vf $(docker ps -a -q)
  ```
