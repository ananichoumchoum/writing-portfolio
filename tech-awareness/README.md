# Tech Awareness Platform
![Documentation Version](https://img.shields.io/badge/docs-v1.0.0-blue)
![Page Updated](https://img.shields.io/badge/last%20updated-June%202025-brightgreen)



A full-stack application designed to raise cybersecurity awareness and empower users through educational content, secure-by-design interactions, and real-time assistance. Features include chatbot integration, secure device image scanning, quizzes, and an admin dashboard.


## Table of Contents

- [Overview](#overview)
- [Technology Stack](#technology-stack)
- [Features](#features)
- [Installation & Setup](#installation--setup)
- [API Reference](#api-reference)
- [Learnings and Roadmap](#learnings-and-roadmap)

---


## Technology Stack

- **Frontend:** React, JavaScript (ES6+), SASS (BEM methodology), Vite
- **Backend:** Node.js, Express
- **Database:** MongoDB
- **Deployment:** Docker, Netlify, CI/CD with GitHub Actions
- **Security:** JWT, Firebase Auth, Role-Based Access Control
- **Tooling:** ESLint, Prettier


## Key Features

-  **AI Chatbot:** Real-time assistant answering cybersecurity-related questions
- **Authentication:** JWT-secured login and registration
- **Responsive Design:** Fully optimized for mobile, tablet, and desktop
- **Educational Content:** Covers online safety, IoT security, tech-facilitated abuse
- **Admin Panel:** Manage users, quizzes, and submitted content
- **Smart Image Scanner:** Detects smart devices using Cloud Vision API
- **Security Quiz:** Dynamic quiz system to test cybersecurity awareness


## Installation & Setup

### Step 1: Clone the Repository
   ```bash
   git clone https://github.com/your-username/tech-awareness.git
   cd tech-awareness
```

### Step 2: Install Dependencies
    npm install

### Step 3: Set Up Environment Variables
Create a .env file in the root directory and add the following in server:
   ```bash
    FIREBASE_API_KEY=<FIREBASE_API_KEY>
    FIREBASE_AUTH_DOMAIN=<FIREBASE_AUTH_DOMAIN>
    FIREBASE_PROJECT_ID=<FIREBASE_PROJECT_ID>
    FIREBASE_STORAGE_BUCKET=<FIREBASE_STORAGE_BUCKET>
    FIREBASE_SENDER_ID=<FIREBASE_SENDER_ID>
    FIREBASE_APP_ID=<FIREBASE_APP_ID>
    FIREBASE_MEASUREMENT_ID=<MEASUREMENTID>>
    OPENAI_API_KEY=<OPENAI API KEY>
    GOOGLE_APPLICATION_CREDENTIALS={
    "type": "service_account",
    "project_id": "<YOUR PROJECT ID>",
    "private_key_id": "<YOUR PRIVATE KEY ID>",
    "private_key": "-----BEGIN PRIVATE KEY-----\n <YOUR PRIVATE KEY>\n-----END PRIVATE KEY-----\n",
    "client_email": "<YOUR CLIENT EMAIL>",
    "client_id": "<YOUR CLIENT ID>",
    "auth_uri": "<YOUR AUTH URI>",
    "token_uri": "https://oauth2.googleapis.com/token",
    "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
    "client_x509_cert_url": "<YOUR CERT URL>"
    }
```

### Step 4: Set Up Environment Variables
Create a .env file in the root directory and add the following in client:
   ```bash
    VITE_FIREBASE_API_KEY=<VITE_FIREBASE_API_KEY>
    VITE_FIREBASE_AUTH_DOMAIN=<VITE_FIREBASE_AUTH_DOMAIN>
    VITE_FIREBASE_PROJECT_ID=<VITE_FIREBASE_PROJECT_ID>
    VITE_FIREBASE_STORAGE_BUCKET=<VITE_FIREBASE_STORAGE_BUCKET>
    VITE_FIREBASE_SENDER_ID=<VITE_FIREBASE_SENDER_ID>
    VITE_FIREBASE_APP_ID=<VITE_FIREBASE_APP_ID>
    VITE_FIREBASE_MEASUREMENT_ID=<VITE_FIREBASE_MEASUREMENT_ID>
```

### Step 5a: To Run Dev Server
 in the base folder for a  netlify dev environment deployment
   ```bash
    npm run build
    npm start 
  ```

### Step 5b: To Run Production Server
 in the base folder for a  netlify dev environment deployment
   ```bash
    npm run build
    npm run deploy
  ```


## API Reference

The following endpoints power the core functionality of the Tech Awareness platform. All APIs are REST-based and return JSON responses.

---

### 🔹 Chatbot API

**Endpoint:** `POST /api/chat-openai`  
**Description:** Processes user questions related to tech abuse or cybersecurity and returns AI-generated guidance.

#### Request Headers
| Header           | Value                |
|------------------|----------------------|
| `Content-Type`   | `application/json`   |

#### Request Body
```json
{
  "queryText": "How can I secure my home Wi-Fi?"
}
```
#### Success Response
```json
{
  "response": "Ensure you use WPA3 encryption and a strong, unique password."
}
```
#### Error Response
```json
{
  "error": "Internal Server Error"
}
```

### 🔹 Cloud Vision API

**Endpoint:** `POST /api/cloudvision`
**Description:**  Processes an image URL using the Google Cloud Vision API to analyze and categorize the image.

#### Request Headers
| Header           | Value                |
|------------------|----------------------|
| `Content-Type`   | `application/json`   |

#### Request Body
```json
{
"imageUrl": "gs://your-bucket-name/path/to/image.jpg"
}
```

#### Success Response
```json
{
    "isIoTDevice": true,
    "isSmartDevice": true,
    "labels": [
    { "description": "Electronic device" },
    { "description": "Smartphone" }
    ],
    "message": "Image processed successfully."
}
```
#### Error Response
```json
{
    "error": "Error processing request"
}
```


## Learnings and Roadmap

### 🔧 Known Issues & Technical Challenges

- **Redux State Persistence:** The application does not consistently clear Redux state when windows or components are closed.
- **Form Auto-Detection:** Dynamic detection of form inputs in React remains unresolved despite multiple implementation attempts.
- **Netlify Function Limitations:** Current serverless setup complicates file uploads and multi-step API handling.
- **User Session Management:** There is no persistent user/session tracking mechanism, which limits personalization and control over OpenAI usage.
- **Build Size Overhead:** Current frontend bundle size exceeds recommended limits for fast deployment and needs optimization.

---

### Planned Enhancements

- **Session Management:** Implement UUID-based user session handling to track interaction history and enforce usage limits.
- **State Management Improvements:** Explore Redux middleware or alternative state libraries to ensure proper state cleanup.
- **File Upload Optimization:** Replace current image upload workflow with pre-signed URLs or BusyBee integration.
- **End-to-End Testing:** Add automated test coverage for chatbot flows and Cloud Vision processing.
- **Build Optimization:** Refactor and modularize frontend code to reduce bundle size and improve deployment times.
- **Form Input Tracking:** Investigate React custom hooks or third-party solutions for improved form auto-detection across dynamic components.
