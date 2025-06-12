# PowerBi-Project-UPI
# 💳 UPI Transactions Analysis – Power BI Project

This Power BI project analyzes UPI transactions using various interactive visuals and slicers for dynamic exploration.

## 📂 Project Files

- **UPI+Transactions.xlsx** – Raw dataset used for analysis
- **UPI_Project.pbix** – Power BI dashboard file

## 🧾 About the Dataset

The dataset contains detailed UPI transaction information with the following columns:

| Column Name               | Description |
|--------------------------|-------------|
| `TransactionID`          | Unique ID for each transaction |
| `TransactionDate`        | Date of transaction |
| `TransactionTime`        | Time of transaction |
| `Amount`                 | Transaction amount |
| `RemainingBalance`       | Balance left after transaction |
| `BankNameSent`           | Bank sending the money |
| `BankNameReceived`       | Bank receiving the money |
| `City`                   | City of the customer |
| `Gender`                 | Gender of the customer |
| `CustomerAge`            | Age of the customer |
| `TransactionType`        | Type of transaction (e.g., Payment, Transfer) |
| `Status`                 | Transaction status (e.g., Success, Failed) |
| `DeviceType`             | Device used for transaction (e.g., Mobile, Laptop) |
| `PaymentMethod`          | How the payment was made (e.g., UPI ID, QR Code) |
| `PaymentMode`            | Scheduled or Instant |
| `Currency`               | Currency used |
| `MerchantName`           | Name of the merchant |
| `Purpose`                | Purpose of the transaction (e.g., Food, Shopping) |
| `CustomerAccountNumber`  | Customer’s account number |
| `MerchantAccountNumber`  | Merchant’s account number |

## ✅ Steps Performed

- Loaded UPI transaction data and checked for missing values and data format.
- Identified that Customer and merchant account number columns were in number format and changed them to text.
- Performed data profiling and checked for errors.
- Used 10 slicers and formatted the following fields:
  - `BankNameSent`
  - `BankNameReceived`
  - `DeviceType`
  - `PaymentMethod`
  - `City`
  - `Gender`
  - `AgeGroup`
  - `TransactionType`
  - `MerchantName`
  - `Purpose`
- Created an `AgeGroup` column from the `CustomerAge` column using conditional logic:
  - Age ≤ 25 → A1  
  - Age ≤ 35 → A2  
  - Else → A3
- Added a line chart showing `Transaction Amount` by month.

## 📊 Page 2

- Created another report page with the same slicers.
- Built a matrix visual with:
  - **Values**: `Transaction Amount`, `Remaining Amount`
  - **Columns**: `City`
  - **Rows**: only Month from `TransactionDate`
- Applied conditional formatting:
  - Low values → 🔴 Red
  - High values → 🟢 Green
- Synced slicers across both pages using the **Sync Slicer** option from the View tab.

## 🔁 Bookmarks

- Created four charts:
  - line and Bar chart of `Transaction Amount` by month (`TransactionDate`)
  - Line and bar charts of `Remaining Amount` by month (`TransactionDate`)
- Used **Bookmarks** to allow users to switch between charts interactively.

