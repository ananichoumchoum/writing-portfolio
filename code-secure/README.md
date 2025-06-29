# Code Secure
![Documentation Version](https://img.shields.io/badge/docs-v1.0.0-blue)
![Page Updated](https://img.shields.io/badge/last%20updated-June%202025-brightgreen)
## Overview

Code Secure is a private web-based platform designed to simulate secure coding challenges through structured Capture The Flag (CTF) exercises. Built with React, it allows users to interact with purpose-built code scenarios that expose common implementation flaws.

Each challenge focuses on a specific security concept, such as improper input validation, exposed client logic, or insecure API behaviors. The objective is to create a guided environment where users can identify, exploit, and understand vulnerabilities within a controlled and educational context.

> ℹ️ The platform is under active development and not publicly accessible. 


## Table of Contents

1. [Overview](#overview)  
2. [Features](#features)  
3. [Installation & Setup](#installation--setup)  
4. [Usage](#usage)   
6. [Development Guide](#development-guide)  
7. [Roadmap](#roadmap)  


## Features

The following table provides a summary of key components available in Code Secure:

| Feature Category     | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| Challenge Engine      | Interactive CTF-style challenges with real-time validation and scoring     |
| UI Interface          | Web-based React frontend with guided navigation and contextual content     |
| Feedback System       | Flag submission, instant response, and remediation guidance                |                   |

---

### Challenge Engine

- Scenario-driven coding challenges with embedded vulnerabilities
- Challenge metadata includes category, difficulty, and remediation type
- Validates user submissions and tracks completion status

### User Interface

- Built with React and Vite
- Interface provides isolated context for each challenge
- Instructional writing embedded throughout each user flow

### Feedback System

- Flag-based scoring with configurable point values
- Immediate feedback with context-aware remediation messages
- Hints available per challenge based on progress


## Installation & Setup

### Prerequisites

- Node.js v18+  
- npm


### Clone the Repository

```bash
git clone https://github.com/ananichoumchoum/code-secure.git
cd code-secure
```


### Install Dependencies
```bash
npm install
```

### Environment Variables
Create a .env.local file in the project root and define the following:
```bash
VITE_API_BASE_URL=http://localhost:3000
VITE_AUTH_TOKEN=your-dev-token
```
>ℹ️ Use .env.production for production deployment environments. Tokens and secrets should never be hardcoded in source.

### Start the Development Server
```bash
npm run dev
```


## Usage

Once the development server is running, navigate to the following URL in your browser:

    http://localhost:5173/


### Challenge Flow

Each challenge follows a consistent pattern:

1. **Select a challenge**  
   Challenges are listed by category and difficulty. You may filter or search based on tags such as “input validation”, “authentication”, or “client-side logic”.

2. **Review the description**  
   Each challenge includes a written scenario, technical context, and objectives.

3. **Explore the environment**  
   You will have access to simulated code, an API endpoint, or a UI component with embedded vulnerabilities.

4. **Submit a flag**  
   Flags must be entered in the expected format (e.g., `FLAG{example}`) and are validated in real time.

5. **View feedback**  
   On submission, you will receive one of the following:
   - Success message and remediation summary
   - Failure response with optional hints


## Development Guide

### Codebase Structure

| Directory       | Purpose                                      |
|------------------|----------------------------------------------|
| `/src/`          | React application source code                |
| `/src/components/` | Reusable UI components                    |
| `/src/views/`    | Page-level views and layout containers       |
| `/src/challenges/` | Challenge definitions and local metadata  |
| `/public/`       | Static assets                                |



### Scripts

| Command            | Description                          |
|--------------------|--------------------------------------|
| `npm run dev`      | Starts the local development server  |
| `npm run build`    | Builds the project for production    |
| `npm run preview`  | Runs a local preview of the build    |
| `docker compose up`| Launches optional local services     |


### Style and Linting

- Follows standard ESLint configuration for React
- Prettier is used for consistent formatting
- Folder structure is modular and feature-scoped

> Developers are expected to follow consistent naming conventions and avoid inline logic in views unless scoped to that component.

## Roadmap

The following improvements and features are currently planned or in progress:

- Add user authentication and role-based access control (RBAC)
- Implement challenge attempt tracking per user
- Expand challenge library with diverse vulnerability types
- Add scoring leaderboard and session grouping
- Introduce testing and validation workflows for challenge logic
- Improve visual feedback and challenge walkthroughs
- Integrate sandboxed API endpoints for advanced challenges

This list will evolve as the platform is tested and refined.

