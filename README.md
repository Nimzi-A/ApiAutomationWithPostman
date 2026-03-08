# API Automation Demo – Postman, Newman & GitHub Actions

This repository demonstrates **API automation testing using Postman collections integrated with CI/CD using Newman and GitHub Actions**.

The goal of this project is to showcase **API testing and automation skills for QA / Test Automation roles**.

The test suite validates REST APIs and runs automatically in a CI pipeline whenever code is pushed to the repository.

---

## Technologies Used

* Postman – API request creation and test scripting
* Newman – Command-line runner for Postman collections
* GitHub Actions – CI/CD pipeline automation
* JSONPlaceholder API – Public REST API used for testing
* JavaScript – Postman test scripts

---

## Project Structure

```
ApiAutomationWithPostman
│
├── postman
│   ├── api-automation.postman_collection.json
│   └── qa-environment.postman_environment.json
│
├── .github
│   └── workflows
│       └── api-tests.yml
│
├── .gitignore
└── README.md
```

---

## Automated API Test Scenarios

The Postman collection includes the following test cases:

| API                    | Description            |
| ---------------------- | ---------------------- |
| GET /users             | Retrieve list of users |
| GET /users/{id}        | Retrieve a single user |
| POST /posts            | Create a new resource  |
| DELETE /posts/{id}     | Delete a resource      |
| GET /users/{invalidId} | Validate 404 response  |

Each request includes automated assertions validating:

* HTTP status codes
* Response body data
* API behaviour for valid and invalid scenarios

Example assertion:

```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

---

## Running Tests Locally

Install Newman:

```
npm install -g newman
```

Run the collection:

```
newman run postman/api-automation.postman_collection.json \
-e postman/qa-environment.postman_environment.json
```

---

## Continuous Integration (CI/CD)

API tests run automatically using **GitHub Actions** whenever code is pushed to the `main` branch.

Workflow location:

```
.github/workflows/api-tests.yml
```

Pipeline steps:

1. Checkout repository
2. Install Node.js
3. Install Newman
4. Execute Postman collection
5. Display test results

---

## Purpose of This Project

This project demonstrates:

* API automation testing using Postman
* Writing API validation scripts
* Running tests using Newman CLI
* Implementing CI/CD pipelines using GitHub Actions
* Managing environment configuration

This repository serves as a **demo project for QA / Test Automation interviews**.

---
