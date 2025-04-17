# Shopify Pincode Validator (Google Sheets Integration)

This Shopify section allows customers to check if delivery is available in their area based on their pincode. It fetches live pincode data from Google Sheets using the Google Sheets API and displays validation messages dynamically.

---

## 🛠 Features

- Custom Shopify section: `Pincode Validator`
- Real-time pincode availability check
- Pincode list stored in Google Sheets
- API-based dynamic validation
- Simple, lightweight, and easily extensible

---

## 🔧 Coding Approach

### 1. Shopify Theme Section
We created a new custom snippts named `pincode-validator.liquid`, which includes:

- A basic HTML structure: an input field, a button, and a result container.
- A script that uses `axios` to call the Google Sheets API.
- Basic validation and conditional logic based on pincode availability.

### 2. Google Sheets as Data Source
- All deliverable pincodes are stored in **Column A** of a public Google Sheet.
- The sheet is **published to the web** for public read-only access.
- The **Google Sheets API** is used to fetch the data.

### 3. API Key and URL Structure
The frontend script hits the following URL:


