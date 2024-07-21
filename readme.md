# Homework 9

For this assignment, I have fixed the repository filled with broken code for a QR Code API. The objective was to understand the errors, run the tests, and ensure that the entire QR program passes GitHub Actions. Below is a detailed summary of what I have done.

# Steps Taken
1. Cloning and Initial Setup

2. Created a Virtual Environment:
python3 -m venv venv

3. Activated the Virtual Environment:
source venv/bin/activate

4. Installed the Required Packages:
pip install -r requirements.txt

5. Created the Necessary Directory:
mkdir qr_codes

This step was crucial to ensure the Docker container had the right permissions to write to the qr_codes directory.

## Debugging and Fixing Code

### Ran pytest in docker and fixed broken tests to ensure they pass successfully.
docker compose exec fastapi pytest 

### Updated Dockerfile:
Streamlined the installation of dependencies.

### Updated production.yml:
Configured GitHub Actions to run tests, build Docker images, and push to DockerHub.
Made sure to set up environment variables and credentials for DockerHub correctly.
Made necessary changes to the production.yml to include my repository information and environment variables.

### Resolved Vulnerabilities:
Updated the gunicorn version to 22.0.0 to address the CVE-2024-1135 vulnerability.
Debugged and Fixed Tests:

### Started the App with Docker:
docker compose up --build

### Accessed the API Documentation:

Opened the browser and navigated to http://localhost/docs to view the OpenAPI spec documentation.
Authorized the API:

Clicked "authorize" and entered the credentials:
Username: admin
Password: secret

Tested API Endpoints:
Used the spec page to test creating, retrieving, and deleting QR codes.
Ensuring CI/CD Pipeline Success

### Updated GitHub Actions Workflow:

### Committed and Pushed Changes:
Ensured that all steps in the CI/CD pipeline passed successfully, including building, and pushing the Docker image.