# Project 3: Flask-Based Student Registration Web App with Jenkins

## Project Title
**Flask-Based Student Registration Web Application Deployed Using Jenkins**

## Objective
Build and automate deployment of a simple student registration app using Flask and Jenkins CI/CD pipeline to demonstrate:

- **Full web app lifecycle**
- **DevOps and Continuous Delivery**

## Technology Stack
- **Backend:** Python (Flask)
- **Database:** MySQL
- **Frontend:** HTML
- **CI/CD:** Jenkins
- **Version Control:** Git, GitHub
- **Utilities:** socat (for port forwarding)

## Implementation Steps

### 1. Flask Application Setup
- Created a simple Flask app with routes to register students and view records.
- Developed frontend using basic HTML forms.
- Used MySQL as the backend database to store student registration data.

### 2. MySQL Database Configuration
- Installed MySQL server locally or on EC2.
- Created a database named `student_registration`.
- Created a table with fields: `id`, `name`, `email`, `course`.

### 3. GitHub Repository Initialization
- Initialized Git in the project directory.
- Pushed code to GitHub under:  
  [Student Registration App Repository](https://github.com/Atharva%20Kishor%20Matale/stud-reg-flask-app/tree/master)

### 4. Jenkins Installation & Configuration
- Installed Jenkins on a local or remote Ubuntu server.
- Installed required plugins:  
  - Git  
  - Pipeline  
  - SSH Agent  
  - Ansible (optional)  
  - Python plugin

### 5. Jenkins Pipeline Creation
- Created a new Jenkins pipeline project.
- Added pipeline script using `Jenkinsfile` with stages:
  - **Clone GitHub Repo**
  - **Install Dependencies** (`pip install -r requirements.txt`)
  - **Start Flask App** (using background execution or with `socat` for port binding)
  - **Archive Flask Log Files** (optional)

### 6. Port Forwarding with socat (Optional)
- Used `socat TCP-LISTEN:5000,fork TCP:localhost:5000` to enable external access to Flask app from Jenkins.

### 7. Testing & Validation
- Triggered the Jenkins job.
- Verified:
  - Flask app starts correctly.
  - Database inserts work via the form.
  - Registered data appears on the display route.

### 8. Final Output
- Functional web app accessible on port 5000 (or configured port).
- Jenkins automatically deploys the latest code on every build.
