# API Trello Testing with Jenkins

## Description

This project demonstrates how to test the Trello API using **Postman** and **Newman**, integrated into a **Jenkins** pipeline. It leverages a Postman collection to run automated API tests and generate test reports.

- Application under test: [Trello](https://trello.com/)
- [API Documentation](https://developer.atlassian.com/cloud/trello/rest/api-group-actions/#api-group-actions)

### Tools Used
- **Postman**: API testing tool.
- **Newman**: Command-line collection runner for Postman.
- **Jenkins**: Automation server for CI/CD.
- **Newman-reporter**: Reporter for enhanced test result visualization.

---

## Types Available for Testing

#### HTTP Methods Supported by Trello API:
- **GET**: Retrieve information (e.g., boards, lists, cards, checklists, members).
- **POST**: Create resources (e.g., new boards, lists, cards, checklists, organizations).
- **PUT**: Update existing resources (e.g., modify boards, lists, cards).
- **DELETE**: Remove resources (e.g., delete boards, cards, checklists, organizations).

### Notes:
- All API requests go to `https://api.trello.com`
- The `/1` part of the URI refers to the API version.
- Endpoints include `/boards`, `/lists`, `/cards`, `/checklists`, `/members`, `/organizations`, etc.

---

## Postman Collection Overview

The file `API_Trello.postman_collection.json` is a Postman collection designed to test various Trello API operations. Below is a summary of its purpose and main features:

1. **Automation of Trello API Testing**  
   The collection automates actions like creating, updating, and deleting Trello resources such as boards, lists, and cards. Each request has predefined tests to validate API responses.

2. **Main Operations Tested**
    - **Creating a board**: Verifies if the board is successfully created by checking for properties like `id`, `name`, and `prefs`.
    - **Deleting a board**: Ensures the board can be deleted, with validation of response status codes.
    - **Creating a list**: Tests the creation of lists on boards, with validation of the list creation process.
    - **Archiving/unarchiving lists**: Includes PUT requests to archive or unarchive lists and confirms these actions.
    - **Creating and updating cards**: Adds cards to lists and updates their properties, with appropriate tests to verify changes.

3. **Test Scripts**  
   JavaScript-based test scripts validate API responses by checking for status codes and specific properties like `id`, `name`, etc.

4. **Dynamic Environment Variables**  
   Environment variables like `{{key}}`, `{{token}}`, `{{board_id}}`, `{{list_id}}` store dynamic data (e.g., API keys or created resource IDs) for reuse in subsequent requests.

5. **Chained Requests**  
   The collection uses values from previous requests to execute dependent actions, such as using a board’s `id` to delete it in the next step.

---

## Example Operations

### Create Requests:
- **Actions**: Create a new board, list, card, checklist, or organization.

### Read (GET) Requests:
- **Actions**: Retrieve information about boards, lists, cards, checklists, or organizations.

### Update (PUT) Requests:
- **Actions**: Modify existing boards, lists, cards, checklists, or organizations.

### Delete Requests:
- **Actions**: Remove boards, cards, checklists, or organizations.

[API Documentation](https://developer.atlassian.com/cloud/trello/rest/api-group-actions/#api-group-actions)

---

## How to Generate the Trello API Token

1. **Create a Trello Account**  
   [Sign up here](https://trello.com/signup).

2. **Generate API Key and Token**  
   - Follow the instructions [here](https://developer.atlassian.com/cloud/trello/guides/power-ups/managing-power-ups/) to generate an API key and token for Postman.

---

## Setup Instructions for newman run

### 1. Install Postman
- Download and install [Postman](https://www.postman.com/).

### 2. Create a Postman Account
- Sign up for a Postman account if you don’t have one already.

### 3. Install Node.js
- Download and install [Node.js](https://nodejs.org/).

### 5. Install Newman
- Install Newman globally using npm:
  ```bash
  npm install -g newman
  
### 4. Run collection with newman
- Open your terminal, navigate to the directory, and run the following command:
    ```bash
    newman run API_Trello.postman_collection.json -e Trello_env.postman_environment.json

### 5. Install [newman-reporter-htmlextra](https://www.npmjs.com/package/newman-reporter-htmlextra)
 - The reporter works as a plugin with Newman so ensure that you have already installed that package globally, using npm install -g newman
      ```bash
   npm install -g newman-reporter-htmlextra


### 6. Run collection with newman html report extra
 - To generate an HTML report using the htmlextra reporter, run this command:
    ```bash
    newman run API_Trello.postman_collection.json -e Trello_env.postman_environment.json --reporters cli,htmlextra --reporter-htmlextra-export newman/reportTest.html
   ```



