# ✈️ Airport API Automated Testing Suite (Bruno)

![API Testing](https://img.shields.io/badge/Testing-Automated-green)
![Bruno](https://img.shields.io/badge/Tool-Bruno-orange)
![JavaScript](https://img.shields.io/badge/Language-JavaScript-yellow)

This repository serves as a showcase of automated REST API testing using **Bruno**. The project demonstrates a testing strategy including **Happy Path** and **Negative Testing**.

---

## 🚀 Key Features & Test Coverage
The suite contains over **100 individual assertions** providing 360° coverage of the API's functionality:

### 1. Functional Testing (Happy Path)
* **Full CRUD Lifecycle:** Testing `/airports` and authenticated `/favorites` endpoints.
* **Business Logic:** Accurate distance calculations (KM/Miles/Nautical) with tolerance thresholds.
* **Data Integrity:** Ensuring ID uniqueness and strict IATA/ICAO formatting via **Regular Expressions**.

### 2. Negative & Security Testing
* **Unauthorized Access:** Validates that private endpoints (like `/favorites`) correctly return `401 Unauthorized` when a valid token is missing.
* **Error Handling:** Verifies `404 Not Found` scenarios and ensures the API returns consistent error contracts.
* **Security Resilience:** Checks that error details do not leak sensitive system information while remaining helpful for the client.

### 3. Advanced Automation Techniques
* **Dynamic Request Chaining:** Automatically extracting and setting authentication tokens from response bodies into environment variables (`bru.setEnvVar`).
* **Contract Testing:** Using iterative schema validation to ensure response structures never break.
* **HATEOAS Validation:** Checking that pagination links are present and correctly formatted.

---

## 📋 Technical Highlights

| Feature | Description |
| :--- | :--- |
| **Performance Gates** | Every request must meet strict response time benchmarks (1000ms - 2000ms). |
| **Defensive Scripting** | Logic accounts for nullable fields and optional attributes to prevent false negatives. |
| **Clean Code** | Helper functions and clear constant definitions for high maintainability. |

---

## 🛠️ Tech Stack
* **[Bruno](https://www.usebruno.com/)** – Modern, Git-friendly, offline-first API client.
* **JavaScript (Chai.js)** – For complex assertions and dynamic scripting.
* **Git/GitHub** – For version control and professional documentation.

---

## 🏃 How to Run the Tests

1.  **Clone this repository:**
    ```bash
    git clone [https://github.com/veronikakurhajcova/airport_gap_with_bruno.git](https://github.com/veronikakurhajcova/airport_gap_with_bruno.git)
    ```
2.  **Open in Bruno:** Select "Open Collection" and point to the cloned folder.
3.  **Set Up Environment:** * Create a new environment in Bruno.
    * Set `baseUrl` to `https://airportgap.com/api`.
    * The `airportgap_token` will be automatically set by the login request.
4.  **Execution:** Use the **Collection Runner** to execute the complete suite.

---

> 👩‍💻 Developed by **Veronika Kurhajcová**. This project reflects a commitment to quality, security, and professional API automation standards.
