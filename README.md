# Full Stack Application

This project is a full-stack application with a React frontend and a Node.js backend. It uses MongoDB for data storage and is deployed on Render.

## Folder Structure
/my-project
  /Backend
    ├── node_modules/
    ├── server.js
    ├── package.json
    └── .env
  /dashboard-app
    ├── node_modules/
    ├── src/
    ├── public/
    ├── package.json
    └── .env
  .gitignore
  README.md
  package.json (Optional - if using concurrently)

## Backend

The backend is built using Express.js, Node.js, and MongoDB.

### Prerequisites

1. [Node.js](https://nodejs.org/) installed
2. MongoDB URI for database connectivity (can be local or cloud-based like MongoDB Atlas)
3. JWT_SECRET for JWT authentication

### How to Run the Backend Locally

1. Navigate to the `Backend` directory:
    ```bash
    cd Backend
    ```
2. Install dependencies:
    ```bash
    npm install
    ```
3. Set up your environment variables (in `.env` file):
    ```
    MONGODB_URI=mongodb://your-mongo-url
    JWT_SECRET=your-jwt-secret
    PORT=3000
    ```
4. Start the server:
    ```bash
    npm run dev
    ```
   The backend should now be running at `http://localhost:3000`.

## Frontend

The frontend is a React-based application created with `create-react-app`.

### How to Run the Frontend Locally

1. Navigate to the `dashboard-app` directory:
    ```bash
    cd dashboard-app
    ```
2. Install dependencies:
    ```bash
    npm install
    ```
3. Set up your environment variables (if necessary).
4. Start the React app:
    ```bash
    npm start
    ```
   The frontend should now be running at `http://localhost:3001` (or the port shown in the terminal).

## How to Run Both Backend and Frontend Simultaneously

You can run both the backend and frontend servers in parallel. If you want to make it easier to run both, you can create a root `package.json` file to manage both projects.

### Example Root `package.json` (optional)

You can set up a root `package.json` to run both the backend and frontend using the `concurrently` package.

1. Install `concurrently` at the root of your project:
    ```bash
    npm install concurrently
    ```
2. Create a `package.json` in the root folder of the project (`/my-project`) with the following content:

```json
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



3. **Git Ignore Setup:**
To ensure that unnecessary files (like `node_modules`, environment files, etc.) are ignored by Git, you need to configure the `.gitignore` file in the root directory.

Example `.gitignore`:

Node.js
node_modules/
Backend
/Backend/node_modules /Backend/.env
Frontend
/dashboard-app/node_modules /dashboard-app/.env
Logs
npm-debug.log* yarn-debug.log* yarn-error.log*	
Misc
.DS_Store

4. **Push to GitHub:**
Once you've made these changes, push your code to a GitHub repository.

```bash
git add .
git commit -m "Added frontend and backend in a single repo, and added README file"
git push origin main


Deployment
Backend Deployment
1.	Deploy the backend on a platform like Render, Heroku, or any cloud provider.
2.	Set the necessary environment variables (e.g., MONGODB_URI, JWT_SECRET, etc.) in the deployment platform.
Frontend Deployment
1.	Deploy the frontend on Render, Vercel, Netlify, or any cloud provider.
2.	Set the API URL to the deployed backend's URL in your frontend application.

