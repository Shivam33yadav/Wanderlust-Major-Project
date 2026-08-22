# 🌍 Wanderlust — Full-Stack Travel Listing Platform

Wanderlust is a **Full-Stack Travel and Property Listing Web Application** inspired by modern travel platforms. It allows users to explore destinations, 
create and manage property listings, upload images, authenticate securely, and share reviews and ratings.

This project demonstrates the practical implementation of **Full-Stack Web Development concepts**, including frontend development, backend development, database management, RESTful routing, 
authentication, authorization, middleware, MVC architecture, CRUD operations, 
image uploads, cloud storage, validation, error handling, and session management.

---

## 🚀 Project Overview

Wanderlust provides a complete platform where users can:

- Browse travel/property listings
- View detailed listing information
- Create new listings
- Edit existing listings
- Delete listings
- Upload listing images
- Store images using Cloudinary
- Register new accounts
- Login and logout securely
- Create ratings and reviews
- Delete reviews
- Associate listings with their owners
- Associate reviews with authenticated users
- Receive success and error flash messages
- Store and retrieve application data using MongoDB

The project follows the **MVC (Model-View-Controller) architecture**, making the application modular, maintainable, scalable, and easier to debug.

---

# 🏗️ MVC Architecture

We have implemented this **Full-Stack Project using the MVC Framework**.

MVC stands for:

- **M — Model**
- **V — View**
- **C — Controller**

The architecture separates the application's data, business logic, and user interface.

### 📦 Model

The Model layer manages the application's database structure and data.

Models used in this project include:

- `models/listing.js`
- `models/review.js`
- `models/user.js`

Mongoose is used to create schemas and communicate with MongoDB.

### 🎮 Controller

The Controller layer contains the application's business logic.

Controllers handle:

- Creating listings
- Reading listings
- Updating listings
- Deleting listings
- Creating reviews
- Deleting reviews
- User authentication
- Processing requests
- Sending responses

Controllers are organized inside the `controllers/` directory.

### 🎨 View

The View layer is responsible for the user interface.

Technologies used include:

- HTML
- CSS
- JavaScript
- Bootstrap
- EJS
- EJS-Mate

Views are organized inside the `views/` directory.

### 🛣️ Routes

Routes define the application's HTTP endpoints and connect user requests to the appropriate controllers.

Examples:

```text
GET     /listings
GET     /listings/:id
GET     /listings/new
POST    /listings
GET     /listings/:id/edit
PUT     /listings/:id
DELETE  /listings/:id

POST    /listings/:id/reviews
DELETE  /listings/:id/reviews/:reviewId

GET     /signup
POST    /signup
GET     /login
POST    /login
GET     /logout
```

### 🔄 MVC Request Flow

```text
User
  ↓
Browser
  ↓
Route
  ↓
Controller
  ↓
Model
  ↓
MongoDB
  ↓
Controller
  ↓
View
  ↓
Browser
```

---

# 🛠️ Technologies Used

## Frontend

- HTML5
- CSS3
- JavaScript
- Bootstrap 5
- EJS
- EJS-Mate
- Responsive Web Design
- Client-Side Form Validation

## Backend

- Node.js
- Express.js
- JavaScript
- RESTful Routing
- Middleware
- Controllers
- MVC Architecture
- Async/Await
- Error Handling

## Database

- MongoDB
- Mongoose
- MongoDB Schemas
- MongoDB Models
- CRUD Operations
- ObjectId References
- Mongoose `populate()`
- MongoDB Operators
- Database Relationships

## Authentication & Security

- Passport.js
- Passport Local Strategy
- Express Session
- Connect Flash
- User Authentication
- Authorization
- Protected Routes
- Password Hashing
- Session Management

## Validation & Error Handling

- Joi
- Custom Express Errors
- Express Error Middleware
- Async Error Handling
- Request Validation
- Form Validation

## Image & File Management

- Multer
- Cloudinary
- Multer Storage Cloudinary
- Image Upload
- Cloud Image Storage

## Development Tools

- Git
- GitHub
- npm
- Nodemon
- VS Code

---

# 📚 Full-Stack Web Development Concepts Implemented

This project covers several important concepts of modern Full-Stack Web Development.

## 🌐 Frontend Development

- HTML5
- CSS3
- JavaScript
- Bootstrap
- Responsive Web Design
- Forms
- Form Validation
- EJS Templates
- Dynamic Rendering
- EJS Layouts
- Reusable Partials
- Client-Side JavaScript
- Flash Messages
- Dynamic UI Components

---

## ⚙️ Backend Development

- Node.js
- Express.js
- HTTP Request/Response Cycle
- Express Router
- Route Parameters
- Query Parameters
- Middleware
- Custom Middleware
- RESTful Routes
- Async/Await
- Promises
- Error Handling
- Modular Backend Architecture
- Controllers
- Business Logic

---

## 🗄️ Database Management

MongoDB and Mongoose are used for storing and managing application data.

Concepts implemented:

- MongoDB
- Mongoose
- Schemas
- Models
- CRUD Operations
- ObjectId
- References
- Relationships
- `populate()`
- `find()`
- `findById()`
- `findByIdAndUpdate()`
- `findByIdAndDelete()`
- `$pull`
- Middleware in Mongoose
- Database Relationships

---

# 🔄 CRUD Operations

The application implements complete CRUD functionality.

| Operation | Implementation |
|-----------|----------------|
| Create | Create listings and reviews |
| Read | View listings and reviews |
| Update | Edit listings |
| Delete | Delete listings and reviews |

### Listing CRUD

```text
Create Listing
      ↓
Read Listing
      ↓
Update Listing
      ↓
Delete Listing
```

---

# 🔐 Authentication & Authorization

The application implements secure user authentication using **Passport.js**.

Users can:

- Sign Up
- Login
- Logout
- Maintain authenticated sessions
- Access protected routes
- Create listings
- Create reviews

### Authentication Flow

```text
User
 ↓
Signup/Login
 ↓
Passport Authentication
 ↓
Session Created
 ↓
Authenticated User
 ↓
Access Protected Routes
```

Authorization middleware is used to restrict certain operations to authenticated users.

---

# 🧩 Middleware

Different types of middleware are implemented throughout the application.

### Authentication Middleware

Checks whether the user is logged in.

```text
Request
   ↓
isLoggedIn
   ↓
Authenticated?
  /      \
Yes       No
 ↓         ↓
Next     Login Page
```

### Validation Middleware

Validates listing and review data before storing it in the database.

### Session Middleware

Maintains user sessions.

### Flash Middleware

Displays success and error messages.

### Error Middleware

Handles application errors and displays a custom error page.

### Method Override

Allows the application to use HTTP methods such as:

```text
PUT
DELETE
```

through HTML forms.

---

# ⭐ Reviews & Ratings System

Authenticated users can:

- Add reviews
- Give ratings from 1 to 5
- View reviews
- Delete reviews

Each review contains:

```text
Comment
Rating
Author
Created At
```

Reviews are connected to listings using MongoDB ObjectId references.

---

# 👤 User Relationships

Users are connected with listings and reviews.

```text
User
 │
 ├── Owns
 │     ↓
 │   Listings
 │
 └── Creates
       ↓
     Reviews
```

---

# 🏠 Listing Relationships

Each listing contains information such as:

```text
Title
Description
Image
Price
Location
Country
Owner
Reviews
```

MongoDB references are used to connect listings with their owners and reviews.

---

# ☁️ Cloudinary Image Upload

The application supports image uploading and cloud storage.

The upload flow is:

```text
User Selects Image
        ↓
      Multer
        ↓
    Cloudinary
        ↓
   Image URL
        ↓
      MongoDB
        ↓
  Listing Display
```

This allows images to be stored externally instead of directly inside the application server.

---

# 🛡️ Validation

Joi is used for server-side validation.

Listing data is validated before being stored in MongoDB.

Review data is also validated before creating a review.

This helps prevent invalid data from entering the database.

---

# 🚨 Error Handling

The application contains centralized error handling.

Custom errors are created using:

```text
ExpressError
```

Async operations are handled using:

```text
wrapAsync
```

The application also includes a centralized Express error-handling middleware.

---

# 💬 Flash Messages

The application uses `connect-flash` to provide feedback to users.

Examples:

```text
✓ Welcome to Wanderlust!

✓ New Listing Created!

✓ Listing Updated!

✓ Listing Deleted!

✓ New Review Created!

✓ Review Deleted!

✗ You must be logged in!

✗ Listing does not exist!
```

---

# 📁 Project Structure

```text
Wanderlust-Major-Project/
│
├── controllers/
│   ├── listings.js
│   ├── reviews.js
│   └── users.js
│
├── models/
│   ├── listing.js
│   ├── review.js
│   └── user.js
│
├── routes/
│   ├── listing.js
│   ├── review.js
│   └── user.js
│
├── views/
│   │
│   ├── layouts/
│   │   └── boilerplate.ejs
│   │
│   ├── includes/
│   │   ├── navbar.ejs
│   │   ├── footer.ejs
│   │   └── flash.ejs
│   │
│   ├── listings/
│   │   ├── index.ejs
│   │   ├── new.ejs
│   │   ├── edit.ejs
│   │   └── show.ejs
│   │
│   ├── users/
│   │   ├── login.ejs
│   │   └── signup.ejs
│   │
│   └── error.ejs
│
├── public/
│   ├── css/
│   │   ├── style.css
│   │   └── rating.css
│   │
│   └── js/
│       └── script.js
│
├── utils/
│   ├── ExpressError.js
│   └── wrapAsync.js
│
├── init/
│   └── index.js
│
├── middleware.js
├── schema.js
├── app.js
├── package.json
├── package-lock.json
└── .gitignore
```

---

# 🔗 Database Architecture

The application uses relationships between three major entities:

```text
             ┌─────────────┐
             │    User     │
             └──────┬──────┘
                    │
             owns / creates
                    │
                    ▼
             ┌─────────────┐
             │   Listing   │
             └──────┬──────┘
                    │
                 contains
                    │
                    ▼
             ┌─────────────┐
             │   Review    │
             └──────┬──────┘
                    │
                 created by
                    │
                    ▼
             ┌─────────────┐
             │    User     │
             └─────────────┘
```

Mongoose references and `populate()` are used to retrieve related documents.

---

# ⚙️ Installation & Setup

## 1. Clone the Repository

```bash
git clone https://github.com/Shivam33yadav/Wanderlust-Major-Project.git
```

## 2. Navigate to the Project

```bash
cd Wanderlust-Major-Project
```

## 3. Install Dependencies

```bash
npm install
```

## 4. Start MongoDB

Make sure MongoDB is running on your system.

The application uses:

```text
mongodb://127.0.0.1:27017/wanderlust
```

## 5. Configure Environment Variables

Create a `.env` file in the root directory.

```env
CLOUD_NAME=your_cloudinary_cloud_name
CLOUD_API_KEY=your_cloudinary_api_key
CLOUD_API_SECRET=your_cloudinary_api_secret
```

Do not upload `.env` to GitHub.

Add this to `.gitignore`:

```text
node_modules/
.env
```

## 6. Start the Application

Using Nodemon:

```bash
nodemon app.js
```

Or using Node:

```bash
node app.js
```

## 7. Open the Application

```text
http://localhost:8080
```

---

# 🔄 Complete Application Flow

```text
                    USER
                      │
                      ▼
              ┌──────────────┐
              │   Frontend   │
              │ HTML/CSS/EJS │
              └──────┬───────┘
                     │
                     ▼
              ┌──────────────┐
              │ Express Route│
              └──────┬───────┘
                     │
                     ▼
              ┌──────────────┐
              │  Middleware  │
              └──────┬───────┘
                     │
                     ▼
              ┌──────────────┐
              │  Controller  │
              └──────┬───────┘
                     │
                     ▼
              ┌──────────────┐
              │    Model     │
              │   Mongoose   │
              └──────┬───────┘
                     │
                     ▼
              ┌──────────────┐
              │   MongoDB    │
              └──────┬───────┘
                     │
                     ▼
              ┌──────────────┐
              │  Controller  │
              └──────┬───────┘
                     │
                     ▼
              ┌──────────────┐
              │     EJS      │
              │    View      │
              └──────┬───────┘
                     │
                     ▼
                    USER
```

---

# 🧠 Key Learning Outcomes

By developing this project, we gained practical experience in:

- Full-Stack Web Development
- MVC Architecture
- Node.js
- Express.js
- MongoDB
- Mongoose
- EJS
- Bootstrap
- RESTful Routing
- CRUD Operations
- Authentication
- Authorization
- Passport.js
- Session Management
- Middleware
- Database Relationships
- Mongoose Population
- Joi Validation
- Error Handling
- Cloudinary
- Image Upload
- Git
- GitHub
- Modular Application Architecture
- Client-Server Communication
- Asynchronous JavaScript
- Backend API Design
- Database Management

---

# 🎯 Project Highlights

### ✅ Full-Stack Application

The project demonstrates complete communication between:

```text
Frontend
   ↕
Backend
   ↕
Database
```

### ✅ MVC Architecture

The application separates:

```text
Models      → Database & Data
Controllers → Business Logic
Routes      → HTTP Request Handling
Views       → User Interface
```

### ✅ Authentication

Passport.js and Express Sessions provide secure user authentication.

### ✅ Authorization

Protected routes prevent unauthorized users from performing restricted operations.

### ✅ Database Relationships

MongoDB references are used to connect:

```text
Users
 ↓
Listings
 ↓
Reviews
```

### ✅ Cloud Storage

Cloudinary is used for storing uploaded listing images.

### ✅ Complete CRUD

The project implements Create, Read, Update, and Delete operations.

---

# 🚀 Future Enhancements

The application can be further improved by adding:

- 🔍 Search and Filtering
- 📍 Location-Based Search
- 🗺️ Map Integration
- 💳 Payment Gateway
- ❤️ Wishlist
- 📧 Email Notifications
- 👤 User Profiles
- ⭐ Advanced Review System
- 🛠️ Admin Dashboard
- 📱 Improved Mobile Responsiveness
- 🚀 Deployment on Render/AWS
- 🔔 Real-Time Notifications

---

# 👨‍💻 Developer

## Shivam Yadav

**B.Tech — Computer Science & Engineering**

GitHub:

https://github.com/Shivam33yadav

---

# ⭐ Acknowledgement

This project was developed as a **Full-Stack Web Development Major Project** to gain practical experience in designing, developing, testing, and managing a complete web application using modern web technologies.

The project demonstrates how frontend, backend, database, authentication, cloud services, and MVC architecture work together to build a real-world web application.

---

# ⭐ Support

If you found this project useful, consider giving the repository a ⭐ on GitHub.

**Thank You! 🚀**
