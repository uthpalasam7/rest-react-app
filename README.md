# REST-React-App

A full-stack web application built with **Node.js (Express)** and **React**. This project demonstrates key features such as CRUD operations, RESTful API integration, user authentication and authorization, frontend and backend validation, real-time updates using **Socket.io**, **MongoDB** integration, image uploads, and dynamic UI rendering.

## Features

- **CRUD Operations**: Create, Read, Update, and Delete posts and user data.
- **RESTful API**: Well-structured REST APIs for seamless client-server communication.
- **Authentication & Authorization**: Secure login and user access control.
- **Validation**:
  - Backend validation with `express-validator`
  - Frontend form validation.
- **Socket.io**: Real-time event-driven updates.
- **MongoDB**: A NoSQL database for data storage.
- **Image Upload**: Upload and manage images.
- **Dynamic UI Rendering**: Interactive and responsive frontend design.

## Project Structure

```
rest-react-app/
├── client/       # React frontend
├── server/       # Node.js backend
```

## Installation

### Prerequisites

- [Node.js](https://nodejs.org/) (v16 recommended)
- [MongoDB](https://www.mongodb.com/)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/uthpalasam7/rest-react-app.git
   cd rest-react-app
   ```

2. Install dependencies for both client and server:
   ```bash
   cd server
   npm install
   cd ../client
   npm install
   ```

3. Set up environment variables:
   - Create a `.env` file in the `server/` directory and add your MongoDB connection URL:
     ```env
     MONGODB_URI=your-mongodb-connection-string
     ```

4. Start the development server:
   - Start the backend:
     ```bash
     cd server
     npm start
     ```
   - Start the frontend:
     ```bash
     cd client
     npm start
     ```

5. Access the app:
   Open your browser and navigate to `http://localhost:3000`.

## API Routes

### Feed Routes

#### GET `/feed/posts`
- **Protected**: Yes
- **Description**: Fetch all posts.

#### POST `/feed/post`
- **Protected**: Yes
- **Validation**:
  - `title`: Minimum 5 characters
  - `content`: Minimum 5 characters
- **Description**: Create a new post.

#### GET `/feed/post/:postId`
- **Protected**: Yes
- **Description**: Fetch a single post by its ID.

#### PUT `/feed/post/:postId`
- **Protected**: Yes
- **Validation**:
  - `title`: Minimum 5 characters
  - `content`: Minimum 5 characters
- **Description**: Update a post by its ID.

#### DELETE `/feed/post/:postId`
- **Protected**: Yes
- **Description**: Delete a post by its ID.

### Auth Routes

#### PUT `/auth/signup`
- **Validation**:
  - `email`: Valid email, unique.
  - `password`: Minimum 5 characters.
  - `name`: Non-empty string.
- **Description**: Register a new user.

#### POST `/auth/login`
- **Description**: Login a user and generate a token.

#### GET `/auth/status`
- **Protected**: Yes
- **Description**: Fetch the current user's status.

#### PATCH `/auth/status`
- **Protected**: Yes
- **Validation**:
  - `status`: Non-empty string.
- **Description**: Update the user's status.

## Tech Stack

### Frontend
- React
- Axios (for API requests)

### Backend
- Node.js
- Express.js
- MongoDB (with Mongoose)
- Socket.io
- Express Validator (for backend validation)

## Contribution

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Description of changes"
   ```
4. Push to the branch:
   ```bash
   git push origin feature-name
   ```
5. Create a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
