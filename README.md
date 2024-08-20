# API Trello Testing with Jenkins

## Description

This project demonstrates how to test the Trello API using Postman and Newman, integrated into a Jenkins pipeline. It uses a Postman collection to run automated API tests and generate test reports.

[documentation](https://developer.atlassian.com/cloud/trello/rest/api-group-actions/#api-group-actions)

### Tools Used:
- **Postman**: API testing tool.
- **Newman**: Command-line collection runner for Postman.
- **Jenkins**: Automation server for CI/CD.
- **Newman-reporter**: Reporter for enhanced test result visualization.

### Types Available for Testing:

#### HTTP Methods Supported by Trello API:
- **GET**
- **POST**
- **PUT**
- **DELETE**

### Example Operations:

#### Create Requests:
- **Actions**: Create a new board, list, card, checklist, or organization.

#### Read (GET) Requests:
- **Actions**: Retrieve information about boards, lists, cards, checklists, and organizations.

#### Update (PUT/PATCH) Requests:
- **Actions**: Modify existing boards, lists, cards, checklists, or organizations.

#### Delete Requests:
- **Actions**: Remove boards, cards, checklists, or organizations.

---

### How the Trello API Token is Created:

1. **Create a Trello account**:  
   [Sign up here](https://developer.atlassian.com/cloud/trello/)
   
2. **Generate API key and token**:  
   - Open [Managing Power-Ups](https://developer.atlassian.com/cloud/trello/guides/power-ups/managing-power-ups/) for instructions.
   - Follow the steps to generate an API key and token for use in Postman.




---

## Setup Instructions

### 1. Install Postman:
- Ensure that [Postman](https://www.postman.com/) is installed and running.

### 2. Create a Postman Account:
- Sign up for a Postman account if you don’t have one already.

### 3. Install Jenkins:
- Download and install [Jenkins](https://www.jenkins.io/).

### 4. Configure Node.js in Jenkins:
- Go to "Manage Jenkins" -> "Global Tool Configuration" and add Node.js as a tool.

### 5. Install Newman:
- Install Newman globally using npm:
  
  ```bash
  npm install -g newman

3. **Set Environment in Postman**:
   - Import the collection and environment in Postman.
   - Replace the API key and token in the environment variables.
  
4. **Run the Collection in Newman**:
   - Use the following command to run the collection in Newman:
   
     ```bash
     newman run API_Trello.postman_collection.json -e Trello_env.postman_environment.json
     ```

