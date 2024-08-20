# API_Trello_Testing_Jenkins


## Description

This project demonstrates how to test the Trello API using Postman and Newman, integrated into a Jenkins pipeline. It uses a Postman collection to run automated API tests and generate test reports.

Tools used: Postman, Newman,Newman-reporter,jenkins

Link to collection : API Trello collection .

Types available for testing

HTTP methods supported by this API are GET, POST, PUT, PATCH, and DELETE. In this section, you can explore and perform tests on various types of operations supported by the Trello API. Some examples for this project includes:

Create Requests:

Actions: Create a new board, list, card, checklist, or organization.
Read (GET) Requests:

Actions: Retrieve information about boards, lists, cards, checklists, and organizations.
Update (PUT/PATCH) Requests:

Actions: Modify existing boards, lists, cards, checklists, or organizations.
Delete Requests:

Actions: Remove boards, cards, checklists, or organizations.









How the token was created for API trello and postman:

[create a account 
https://developer.atlassian.com/cloud/trello/ open this link
click Managing Power-Ups
](https://developer.atlassian.com/cloud/trello/guides/power-ups/managing-power-ups/) instruction for genereate apy key and token

link to enviroment

import collection and enviroment in the postman

You need to change key and token in the environment





## Setup

1.Install postman
-make sure [postman](https://www.postman.com/) is istalled and running

2.Create an postman account

1. **Install Jenkins**:
   - Make sure [Jenkins](https://www.jenkins.io/) is installed and running.

2. **Configure Node.js**:
   - Add Node.js as a tool in Jenkins. You can do this from "Manage Jenkins" -> "Global Tool Configuration".

3. **Install Newman**:
   - Install Newman globally using npm:
     ```bash
     npm install -g newman
     ```

