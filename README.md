# ✈️ Airport API Automated Testing Suite (Bruno)

Professional API automation project demonstrating a complete **CRUD lifecycle** and **deep data integrity validation** using the [Bruno](https://www.usebruno.com/) API client and JavaScript.

## 🚀 Key Features & Test Coverage

### 1. Functional Testing (Happy Path)
* **Full CRUD Workflow:** Seamlessly testing `/airports` and authenticated `/favorites` endpoints.
* **Dynamic Data Chaining:** Using `bru.setEnvVar()` to capture IDs and attributes from responses and injecting them into subsequent requests.
* **Business Logic Validation:** * Verification of distance calculations between airports.
    * IATA/ICAO code format validation using Regular Expressions (Regex).
    * GPS coordinate range checks and altitude realism.

### 2. Advanced Data Integrity & Regression
* **Baseline State Comparison:** Capturing the initial state of an object and asserting that non-modified attributes (like airport details) remain unchanged after a `PATCH` request.
* **Geospatial Precision:** Using `.closeTo()` assertions with specific tolerances to handle floating-point precision in GPS coordinates.
* **Contract Testing:** Comprehensive JSON Schema validation for nested objects (airport details, timezone, and notes).

### 3. Negative & Security Testing (Enhanced)
* **Distance Logic Edge Cases:**
    * **Missing Parameters:** Validating `422 Unprocessable Entity` when required `from` or `to` codes are missing.
    * **Invalid Inputs:** Testing response behavior for non-existent IATA codes.
    * **Zero Distance:** Verifying that distance between the same airport (e.g., KORD to KORD) returns a correct `0` value.
* **Security & Authentication:** * **Unauthorized Access:** Strictly validating `401 Unauthorized` responses when the Bearer token is missing or invalid.
    * **Validation Errors:** Testing `422 Unprocessable Entity` for duplicate entries or malformed data.
* **Resource Safety:** Ensuring `404 Not Found` for non-existent resource IDs in the favorites module.

## 🔐 Security & Environment Setup

This project follows security best practices by using **Secret Variables** for sensitive data. 

1. **Environment Configuration:**
   - Open the **Environment Manager** in Bruno.
   - Create a new environment (e.g., `Production`).
   - Add a variable named `token`. 
   - Set the type to **Secret** to ensure it is masked and not stored in plain text within the collection files.

2. **Required Variables:**
   - `baseUrl`: `https://airportgap.com/api`
   - `token`: `Your_Secret_Bearer_Token`

*Note: All other variables (like `fid`, `expectedId`, etc.) are managed dynamically by the scripts during execution.*

## 📋 Technical Highlights

| Feature | Description |
| :--- | :--- |
| **Performance Gates** | Each request must respond within **2000ms**. |
| **Defensive Scripting** | Scripts handle nullable fields and optional attributes to prevent false negatives. |
| **Clean Code** | Use of helper functions and centralized constants for high maintainability. |
| **Automated Cleanup** | Every test cycle ends with a `DELETE` request to ensure an idempotent testing environment. |

## 🛠️ Tech Stack
* **Bruno** – Modern, Git-friendly API client.
* **JavaScript (Chai.js)** – For complex assertions and dynamic logic.
* **AirportGap API** – The target REST API for testing.

## 🏃 How to Run the Tests

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/veronikakurhajcova/airport_gap_with_bruno.git](https://github.com/veronikakurhajcova/airport_gap_with_bruno.git)
    ```
2.  **Open in Bruno:** Select "Open Collection" and point to the cloned folder.
3.  **Setup Environment:**
    * Create a new Environment in Bruno.
    * Set `baseUrl` to `https://airportgap.com/api`.
    * Add your `token` as a secret variable.
4.  **Execute:** The collection is designed to run in sequence. The first GET request automatically populates necessary variables (`fid`, `expectedId`, etc.) for the rest of the suite.

---
**Developed by Veronika Kurhajcová** *Focused on building robust, scalable, and maintainable automated testing solutions.*
