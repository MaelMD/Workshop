# Workshop

Certainly! Here's the complete README file content for your GitHub repository:

```markdown
# Prisma ORM Workshop with NestJS

This repository contains the code and instructions for a workshop on integrating Prisma ORM with a NestJS application. The workshop is divided into three parts:

## Part 1: NestJS Code with Teachers and Students Resources

In this part, we'll create a NestJS application with "Teacher" and "Student" resources and implement CRUD operations for them.

### Getting Started

1. Create a new NestJS project using the Nest CLI:

   ```bash
   nest new prisma-workshop
   ```

2. Define your data models for "Teacher" and "Student" in the `src/teachers` and `src/students` folders, respectively. Use decorators to specify database columns, relations, and validation rules.

3. Generate controllers and services for both "Teacher" and "Student" entities using the Nest CLI:

   ```bash
   nest generate controller teachers
   nest generate service teachers
   nest generate controller students
   nest generate service students
   ```

4. Implement CRUD operations in the controllers and services for both entities, including endpoints for creating, reading, updating, and deleting records.

5. Define routes for each entity in the `app.module.ts` file and connect them to their respective controllers.

6. Run your NestJS application:

   ```bash
   npm run start
   ```

7. Test the CRUD operations using a tool like Postman or Thunder Client.

## Part 2: Install Postgres Docker Image

In this part, we'll set up a PostgreSQL database using a Docker container.

### Getting Started

1. Ensure Docker is installed on your system. You can download and install Docker from the official website: [Docker](https://www.docker.com/get-started)

2. Pull the official PostgreSQL Docker image:

   ```bash
   docker pull postgres
   ```

3. Create and run a PostgreSQL container:

   ```bash
   docker run --name prisma-postgres -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres
   ```

   Replace `"mysecretpassword"` with your desired PostgreSQL password.

4. Verify that the PostgreSQL container is running:

   ```bash
   docker ps
   ```

## Part 3: Integrate Prisma with NestJS and Test CRUD Operations

In this part, we'll integrate Prisma ORM into our NestJS application for database operations and test the CRUD operations.

### Getting Started

1. Install Prisma globally:

   ```bash
   npm install -g prisma
   ```

2. Initialize Prisma in your NestJS project:

   ```bash
   prisma init
   ```

3. Define your data model using Prisma's schema file (`schema.prisma`). Create models for "Teacher" and "Student" entities and their respective database tables.

4. Generate the Prisma Client:

   ```bash
   npx prisma generate
   ```

5. Integrate Prisma into your controllers and services. Update your NestJS controllers and services to use the Prisma Client for database operations.

6. Test the CRUD operations on your NestJS application with Prisma integration using Postman or Thunder Client.

## Additional Notes

- Make sure to create clear documentation or a README file in your GitHub repository to guide your classmates on how to set up and run the project, including instructions for running the PostgreSQL container and integrating Prisma.

- Don't forget to provide the GitHub repository link to your classmates so they can access the code and follow along with the workshop.

Enjoy the workshop and happy coding!
```

You can copy and paste this content into a `README.md` file in your GitHub repository for your classmates to access and follow along with the workshop.
