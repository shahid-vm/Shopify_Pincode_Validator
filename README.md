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

### 4. Create a block in `main-product.liquid`, and call block to on product page please refer the below code 

//block code 
{
      "type": "pincode_Checker",
      "name": "pincode_Checker",
      "settings": [
      ]
    }, 

//render code 

{%- when 'pincode_Checker'-%}
                {% render 'pincode-validator' %}

### 5. test login 

----------------------------------------------------------------------------------------------------------

https://sheets.googleapis.com/v4/spreadsheets/YOUR_SHEET_ID/values/Sheet1!A:A?key=YOUR_API_KEY 

- `YOUR_SHEET_ID` = from the Google Sheet URL
- `Sheet1` = your tab name
- `YOUR_API_KEY` = generated from Google Cloud Console

### 4. JavaScript Logic
- User enters a pincode → clicks "Check Availability"
- Script fetches all pincodes from the Google Sheet
- If the entered pincode exists in the list → show ✅ Delivery Available
- Else → show ❌ Delivery Not Available

### 5. Optional Security
- The API key can be restricted to work only from your Shopify domain.
- You may create a proxy via Google Apps Script for a secure setup if needed.

---

## 🚀 How to Use

1. **Add the Liquid Section**
   - Copy `pincode-validator.liquid` to your `/sections/` folder in your Shopify theme.

2. **Include the Section in Product Page**
   - Add this line in your `product.liquid` or `main-product.liquid`:
     ```liquid
     {% section 'pincode-validator' %}
     ```

3. **Publish & Test**
   - Save changes and preview the product page.
   - Enter a test pincode and validate functionality.

---

## 📌 Notes

- Make sure your Google Sheet is published to the web.
- Don’t forget to replace `YOUR_SHEET_ID` and `YOUR_API_KEY` in the script.

---

## 🙋‍♂️ Need Help?

Feel free to open an issue or reach out for support if you need help setting up the Google Sheet, API key, or integrating this with a custom Shopify theme.



