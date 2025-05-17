# 🧪 Todo API Test Suite (Postman)

This repository contains a comprehensive Postman-based test suite for validating the [Todo API](https://github.com/ovansa/todo-api). It covers core functionalities such as authentication, user registration, and todo operations.

## 📁 Project Structure

```
.
├── todo-api.postman_collection.json   # Main Postman test collection
├── todo-api.postman_environment.json  # Postman environment with variables
├── .github
│   └── workflows
│       └── postman-tests.yml          # GitHub Actions workflow for CI testing
└── README.md
```

## 🚀 Running Tests Locally

### Prerequisites

* [Node.js](https://nodejs.org/) (v18+ recommended)
* [Newman CLI](https://www.npmjs.com/package/newman)

### Install Newman and HTML Reporter

```bash
npm install -g newman newman-reporter-html
```

### Run Tests

```bash
newman run todo-api.postman_collection.json \
  -e todo-api.postman_environment.json \
  -r cli,html \
  --reporter-html-export test-results.html
```

The test report will be saved as `test-results.html`.

---

## 🧪 CI with GitHub Actions

This repo includes a GitHub Actions workflow to automatically run tests on:

* Push to `main`
* Pull requests targeting `main`
* Manual trigger via workflow\_dispatch

### ✅ Run Locally via [`naktos`](https://github.com/usebruno/naktos)

You can also run the GitHub Actions workflow locally using [Naktos](https://github.com/usebruno/naktos):

```bash
naktos run .github/workflows/postman-tests.yml
```

---

## ✅ Covered Test Scenarios

* ✅ User registration (valid & invalid cases)
* ✅ User login (success & failure)
* ✅ Todo creation
* ✅ Input validation
* ✅ Token-based authentication

---

## 🛠 Related Projects

* [Todo API (Go)](https://github.com/ovansa/todo-app-go) — The backend this suite tests.

