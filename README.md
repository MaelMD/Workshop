# Workshop

## Part 1: Setting Up NestJS with Teacher and Student Resources

In this part of the workshop, we will set up a NestJS application and create resources for "Teachers" and "Students." We will implement CRUD (Create, Read, Update, Delete) operations for these resources.

### Step 1: Create a New NestJS Project

1. Start by creating a new NestJS project using the Nest CLI:

   ```bash
   nest new prisma-workshop
   ```

   This command will generate the basic structure of your NestJS application.

### Step 2: Define Your Data Models

2. In this step, you'll define the data models for "Teacher" and "Student." These models will represent the structure of your database tables. Create two entities in the following folders:

   - For "Teacher" entity: `src/teachers`
   - For "Student" entity: `src/students`

   Use decorators to specify database columns, relations, and validation rules for these entities.

### Step 3: Generate Controllers and Services

3. Generate controllers and services for both "Teacher" and "Student" entities using the Nest CLI:

   ```bash
   nest generate controller teachers
   nest generate service teachers
   nest generate controller students
   nest generate service students
   ```

   These commands will create controller and service files for each entity.

### Step 4: Implement CRUD Operations

4. In the controllers and services you've generated, implement CRUD operations for both "Teacher" and "Student" entities. This includes creating endpoints for creating, reading, updating, and deleting records for each resource.

### Step 5: Define Routes and Wiring

5. Define routes for each entity in the `app.module.ts` file and connect them to their respective controllers. This will wire up the routes to the corresponding controller methods.

### Step 6: Test Your NestJS Application

6. Run your NestJS application using the following command:

   ```bash
   npm run start
   ```

   You can now test the CRUD operations using a tool like Postman or Thunder Client to interact with your API.

That's it for Part 1! You've successfully set up a NestJS application with "Teacher" and "Student" resources and implemented CRUD operations. In the next parts of the workshop, we will integrate Prisma ORM and set up a PostgreSQL database to enhance your application further.

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

**Prisma Schema:**

```prisma
// schema.prisma

model Teacher {
  id             Int      @id @default(autoincrement())
  name           String
  age            Int
  phoneNumber    String
  address        String
  numberOfClasses Int
}

model Student {
  id                Int      @id @default(autoincrement())
  name              String
  age               Int
  address           String
  parentsPhoneNumber String
}
```

4. Generate the Prisma Client:

   ```bash
   npx prisma generate
   ```

5. Integrate Prisma into your controllers and services. Update your NestJS controllers and services to use the Prisma Client for database operations.

6. Test the CRUD operations on your NestJS application with Prisma integration using Postman or Thunder Client.

**Dummy Data:**

```json
// Dummy Teachers Data
[
  {
    "name": "John Smith",
    "age": 35,
    "phoneNumber": "+1234567890",
    "address": "123 Main Street, Cityville",
    "numberOfClasses": 3
  },
  {
    "name": "Alice Johnson",
    "age": 28,
    "phoneNumber": "+9876543210",
    "address": "456 Elm Avenue, Townsville",
    "numberOfClasses": 2
  }
]

// Dummy Students Data
[
  {
    "name": "Emma Davis",
    "age": 15,
    "address": "789 Oak Lane, Villagetown",
    "parentsPhoneNumber": "+1112223333"
  },
  {
    "name": "Michael Wilson",
    "age": 16,
    "address": "567 Pine Road, Suburbia",
    "parentsPhoneNumber": "+4445556666"
  }
]
```
