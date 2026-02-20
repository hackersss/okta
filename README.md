# FastAPI and React TypeScript Application

This project is a web application that integrates a FastAPI backend with a React TypeScript frontend. The application implements a login flow using Okta SAML 2.0, manages user data, and provides secure access to AWS S3 resources.

## Project Structure

```
fastapi-react-app
├── backend
│   ├── app
│   │   ├── api
│   │   │   ├── auth.py         # Handles authentication using Okta SAML 2.0
│   │   │   ├── s3.py           # Manages S3 operations and presigned URLs
│   │   │   └── users.py         # User management endpoints
│   │   ├── core
│   │   │   ├── config.py       # Configuration settings for the application
│   │   │   └── security.py     # Security-related functions
│   │   ├── models
│   │   │   └── user.py         # User model for mock users table
│   │   ├── schemas
│   │   │   └── user.py         # Pydantic schemas for user data
│   │   ├── main.py             # Entry point of the FastAPI application
│   │   └── utils
│   │       └── s3_helper.py    # Helper functions for S3 interactions
│   ├── requirements.txt         # Dependencies for the backend application
│   ├── venv                     # Virtual environment for the backend
│   └── README.md                # Documentation for the backend application
├── frontend
│   ├── public
│   │   └── index.html           # Main HTML file for the React application
│   ├── src
│   │   ├── components
│   │   │   ├── Login.tsx        # Login component for user authentication
│   │   │   └── Dashboard.tsx    # Dashboard component for displaying user data
│   │   ├── services
│   │   │   ├── authService.ts   # Functions for handling authentication
│   │   │   └── s3Service.ts     # Functions for interacting with S3
│   │   ├── App.tsx              # Main component of the React application
│   │   └── index.tsx            # Entry point for the React application
│   ├── package.json             # Configuration file for npm
│   ├── tsconfig.json            # TypeScript configuration file
│   └── README.md                # Documentation for the frontend application
└── README.md                    # Overall documentation for the project
```

## Backend Setup

1. Navigate to the `backend` directory:
   ```
   cd fastapi-react-app/backend
   ```

2. Create a virtual environment:
   ```
   python3 -m venv venv
   ```

3. Activate the virtual environment:
   - On macOS/Linux:
     ```
     source venv/bin/activate
     ```
   - On Windows:
     ```
     venv\Scripts\activate
     ```

4. Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```

5. Run the FastAPI application:
   ```
   uvicorn app.main:app --reload
   ```

## Frontend Setup

1. Navigate to the `frontend` directory:
   ```
   cd fastapi-react-app/frontend
   ```

2. Install the required npm packages:
   ```
   npm install
   ```

3. Start the React application:
   ```
   npm start
   ```

## Usage

- Access the application at `http://localhost:8000` for the backend and `http://localhost:3000` for the frontend.
- Follow the login flow using Okta SAML 2.0.
- Users can upload files to their specific folders in S3, ensuring security at both the backend and IAM levels.

## Deployment

This application can be hosted on a remote Ubuntu server using Nginx. Ensure to configure Nginx to serve both the FastAPI backend and the React frontend appropriately.