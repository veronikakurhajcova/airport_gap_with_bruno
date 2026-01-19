# Airport API Automated Testing Suite (Bruno)

This repository serves as a showcase of automated REST API testing using **Bruno**. The project focuses on contract validation, data integrity, and functional logic for the **Airport Gap API**.

---

## 🚀 Key Features Demonstrated
The project consists of three comprehensive test scenarios (requests) covering over **40 individual assertions**:

### 1. Get All Airports (`/airports`)
* **Collection Validation:** Verifying array structures and uniqueness of IDs.
* **Geographic Data:** Validating Latitude/Longitude ranges and realistic altitude values.
* **Format Consistency:** Using Regular Expressions (Regex) to validate IATA and ICAO airport codes.

### 2. Get Single Airport (`/airports/:id`)
* **Schema Validation:** Dynamic checking of data types (*string, number, null*) against a predefined schema.
* **Required Fields:** Ensuring all mandatory attributes are present and non-empty.
* **Data Integrity:** Verifying that the returned record matches the requested ID.

### 3. Calculate Distance (`/airports/distance`)
* **Logic Testing:** Validating computational output and relationships between objects.
* **Nested Structures:** Testing deeply nested objects for both "from" and "to" airport attributes.
* **Metric Verification:** Ensuring numerical precision for kilometers, miles, and nautical miles.

---

## 🛠️ Tech Stack
* **[Bruno](https://www.usebruno.com/)** – An open-source, offline-first API client.
* **JavaScript (Chai.js)** – For advanced scripting and custom assertions.
* **Git/GitHub** – Version control and project management.

---

## 📋 Highlights of the Test Scripts
* **Schema & Type Checking:** Ensuring high API reliability through strict type validation.
* **Performance Benchmarking:** Verifying server response times (Response time < 2000ms).
* **Data Quality:** Using JavaScript logic to check for duplicates and whitespace issues.

---

## 🏃 How to Run the Tests
1.  **Download and install** [Bruno](https://www.usebruno.com/).
2.  **Clone this repository:**
    ```bash
    git clone [https://github.com/veronikakurhajcova/airport_api_tests_bruno.git](https://github.com/veronikakurhajcova/airport_api_tests_bruno.git)
    ```
3.  **Open the collection:** In Bruno, click "Open Collection" and select the project folder.
4.  **Run the suite:** Use the "Collection Runner" to execute all tests.

---

> Developed by **Veronika Kurhajcová** as a demonstration of QA Automation skills.
