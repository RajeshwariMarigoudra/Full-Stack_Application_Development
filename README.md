Full Stack Application
This project is a full-stack application with a React frontend and a Node.js backend. It uses MongoDB for data storage and is deployed on Render.

Folder Structure
 /Full-Stack_Application_Development
/Backend ├── node_modules/ ├── server.js ├── package.json └── .env /dashboard-app ├── node_modules/ ├── src/ ├── public/ ├── package.json └── .env .gitignore README.md package.json (Optional - if using concurrently)

Backend
The backend is built using Express.js, Node.js, and MongoDB.

Prerequisites
Node.js installed
MongoDB URI for database connectivity (can be local or cloud-based like MongoDB Atlas)
JWT_SECRET for JWT authentication
How to Run the Backend Locally
Navigate to the Backend directory:
cd Backend
Install dependencies:
npm install
Set up your environment variables (in .env file):
MONGODB_URI=mongodb://your-mongo-url
JWT_SECRET=your-jwt-secret
PORT=3000
Start the server:
npm run dev
The backend should now be running at http://localhost:3000.
Frontend
The frontend is a React-based application created with create-react-app.

How to Run the Frontend Locally
Navigate to the dashboard-app directory:
cd dashboard-app
Install dependencies:
npm install
Set up your environment variables (if necessary).
Start the React app:
npm start
The frontend should now be running at http://localhost:3001 (or the port shown in the terminal).
How to Run Both Backend and Frontend Simultaneously
You can run both the backend and frontend servers in parallel. If you want to make it easier to run both, you can create a root package.json file to manage both projects.

Example Root package.json (optional)
You can set up a root package.json to run both the backend and frontend using the concurrently package.

Install concurrently at the root of your project:
npm install concurrently
Create a package.json in the root folder of the project (/my-project) with the following content:
{
  "name": "my-project",
  "version": "1.0.0",
  "scripts": {
    "start": "concurrently \"npm run start --prefix Backend\" \"npm run start --prefix dashboard-app\"",
    "dev": "concurrently \"npm run dev --prefix Backend\" \"npm run start --prefix dashboard-app\""
  },
  "dependencies": {
    "concurrently": "^7.0.0"
  }
}


With this setup:

Run both backend and frontend in development mode with:

npm run dev

Run both backend and frontend in production mode with:

npm run start



3. **Git Ignore Setup:**
To ensure that unnecessary files (like `node_modules`, environment files, etc.) are ignored by Git, you need to configure the `.gitignore` file in the root directory.

Example `.gitignore`:
