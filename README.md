# 🚚 Logistics & Last-Mile Delivery Data Quality Analysis

## 📌 Project Overview

This project focuses on cleaning, validating, and transforming logistics and last-mile delivery data using **Python, Pandas, SQL, and Excel**.

Logistics companies collect data from shipment bookings, tracking systems, delivery events, route information, and proof-of-delivery records. However, this data can contain missing values, inconsistent formats, duplicate records, invalid amounts, and incorrect timestamps.

The goal of this project is to improve data quality and prepare reliable data for logistics reporting and analysis.

## 🎯 Project Objectives

* Identify and handle missing values.
* Detect duplicate and inconsistent records.
* Standardize shipment statuses and exception reasons.
* Validate route and stop sequence numbers.
* Check proof-of-delivery information.
* Compare promised and actual delivery timestamps.
* Validate financial values and currency codes.
* Identify missing parent-shipment links.
* Protect customer personal information.
* Detect suspicious tracking IDs and unresolved locations.
* Prepare structured data for further analysis and reporting.

## 🛠️ Technologies Used

| Technology       | Purpose                                   |
| ---------------- | ----------------------------------------- |
| Python           | Data cleaning and validation              |
| Pandas           | Data manipulation and transformation      |
| Jupyter Notebook | Writing and executing analysis code       |
| SQL              | Data validation and analytical queries    |
| Microsoft Excel  | Data inspection and reporting             |
| Git              | Version control                           |
| GitHub           | Project collaboration and code management |

## 📂 Project Structure

```text
logistics-data-science-project/
│
├── data/
│   ├── raw/
│   │   └── shipments.csv
│   │
│   └── processed/
│       ├── shipments_masked.csv
│       └── shipments_tested.csv
│
├── notebooks/
│   ├── Logistics_Data_Quality_Testing.ipynb
│   └── Exploratory_Data_Analysis.ipynb
│
├── src/
│   └── data_cleaning.py
│
├── sql/
│   ├── data_quality_queries.sql
│   └── analytics_queries.sql
│
├── reports/
│   └── project_report.md
│
├── requirements.txt
├── .gitignore
└── README.md
```

*Note: This is a suggested structure. Keep only the folders and files that actually exist in your repository.*

## 📊 Dataset Description

The project uses a logistics shipment dataset containing shipment details, tracking events, delivery information, route details, financial values, and customer information.

The dataset contains **10,000 rows and 35 columns**, based on the initial inspection.

### Important Columns

| Column                 | Description                            |
| ---------------------- | -------------------------------------- |
| `Shipment_ID`          | Unique shipment identifier             |
| `Parent_Shipment_ID`   | Reference to a related parent shipment |
| `Order_Status`         | Order or shipment order status         |
| `Tracking_ID`          | Shipment tracking identifier           |
| `Parcel_ID`            | Parcel identifier                      |
| `Carrier`              | Delivery carrier                       |
| `Service_Level`        | Delivery service category              |
| `Event_TS`             | Timestamp of a shipment event          |
| `Promised_Delivery_TS` | Promised delivery timestamp            |
| `Event_Code`           | Shipment event code                    |
| `Status`               | Event or delivery status               |
| `Origin_Depot`         | Shipment origin depot                  |
| `Destination_Zone`     | Delivery destination zone              |
| `Route_ID`             | Route identifier                       |
| `Stop_Seq`             | Stop sequence number                   |
| `Attempt_No`           | Delivery attempt number                |
| `POD_ID`               | Proof-of-delivery identifier           |
| `Exception_Reason`     | Delivery exception or failure reason   |
| `Freight_Cost`         | Freight cost                           |
| `Surcharge`            | Additional charge                      |
| `COD_Amount`           | Cash-on-delivery amount                |
| `Claim_Amount`         | Claim amount                           |
| `Currency`             | Currency code or label                 |
| `Customer_Name`        | Customer name                          |
| `Customer_Phone`       | Customer phone number                  |
| `Street_Address`       | Customer street address                |

**Important:** One shipment may have multiple event records. Therefore, repeated shipment IDs or tracking IDs are not automatically duplicate errors.

## 🧹 Data Quality Test Cases

The project includes the following validation tasks.

| Test Case | Description                                                                          |
| --------- | ------------------------------------------------------------------------------------ |
| TC01–TC09 | Additional data cleaning and validation tasks, depending on project implementation   |
| TC10      | Normalize route and stop sequence numbers; detect duplicate or skipped stops         |
| TC11      | Validate proof-of-delivery links to shipments and delivery attempts                  |
| TC12      | Standardize exception and failure reason codes                                       |
| TC13      | Compare promised and actual delivery timestamps                                      |
| TC14      | Identify missing pickup or delivery events                                           |
| TC15      | Detect possible event timestamp ordering issues                                      |
| TC16      | Exclude test, cancelled, and voided orders from standard metrics                     |
| TC17      | Validate financial amounts and standardize currency labels                           |
| TC18      | Validate parent-shipment links                                                       |
| TC19      | Mask customer personal information                                                   |
| TC20      | Flag tracking IDs associated with multiple active shipments and unresolved locations |

*TC01–TC09 are placeholders for other tests if they are part of the project. Update this section to match the tests actually implemented.*

## 📁 Output Files

### 1. `shipments_masked.csv`

A version of the dataset in which customer names, phone numbers, and street addresses are masked.

**Purpose:** To reduce exposure of customer personal information when sharing data.

### 2. `shipments_tested.csv`

A dataset containing additional columns created during data quality testing.

These may include validation results for timestamps, route sequences, and financial amounts.

**Purpose:** To support data quality review and further analysis.

**Privacy warning:** Check that `shipments_tested.csv` does not contain unmasked customer information before sharing it publicly.

## ⚙️ Installation and Setup

### Step 1: Install Python

Install Python on your computer if it is not already installed.

### Step 2: Clone the Repository

Open the terminal and run:

```bash
git clone https://github.com/SumanSekhar-Sahoo/logistics-data-science-project.git
```

### Step 3: Open the Project

```bash
cd logistics-data-science-project
```

Open the folder in Visual Studio Code.

### Step 4: Install Required Libraries

```bash
python -m pip install pandas jupyter openpyxl
```

If your project uses additional libraries, add them to `requirements.txt` and install them as needed.

### Step 5: Run the Jupyter Notebook

1. Open `Logistics_Data_Quality_Testing.ipynb`.
2. Select a Python kernel.
3. Run the notebook cells from top to bottom.
4. Review the validation results.
5. Inspect flagged records before making corrections.

Ensure that the CSV file path in the notebook matches your actual folder structure.

## 📈 Expected Outcomes

After running the implemented checks, the project should help identify:

* Missing and invalid data.
* Inconsistent exception labels.
* Potential route sequence problems.
* Missing proof-of-delivery information.
* Possible late deliveries.
* Missing pickup or delivery events.
* Suspicious financial values.
* Unresolved parent-shipment relationships.
* Tracking IDs associated with multiple active shipments.
* Customer information that needs masking before sharing.

The results can support more reliable logistics reporting and further analysis.

**Note:** Flagged records require investigation. A validation flag does not automatically prove that a record is incorrect.

## 🔐 Data Privacy

This dataset may contain personal customer information.

* Do not publish unmasked customer names, phone numbers, or street addresses.
* Keep raw data in a private location.
* Share masked data when appropriate.
* Use `.gitignore` to prevent sensitive raw files from being committed accidentally.
* Check the repository's existing history if sensitive data has already been committed.

## 🚀 Future Improvements

* Create SQL queries for data quality validation.
* Build a dashboard for delivery performance.
* Calculate on-time delivery rates using validated delivery events.
* Compare carrier performance.
* Analyze common delivery exceptions.
* Improve route and location validation using reference data.
* Automate data cleaning and validation.
* Add unit tests for the cleaning functions.

## 👥 Project Team

**Project:** Logistics & Last-Mile Delivery Data Quality Analysis

**Project Type:** Data Science / Data Analytics

**Tools:** Python, Pandas, SQL, Excel, Jupyter Notebook, Git, and GitHub

Add your team members' names and individual responsibilities here.
## 👥 Project Team

This project is a collaborative effort focused on logistics and last-mile delivery data quality analysis using Python, Pandas, SQL, and Excel.

| S. No. | Team Member          | GitHub Profile                                                          |
| -----: | -------------------- | ----------------------------------------------------------------------- |
|      1 | Suman Sekhar Sahoo   | [SumanSekhar-Sahoo](https://github.com/SumanSekhar-Sahoo)               |
|      2 | Pankaj Kumar Behera  | [Pankaj-k-Coder](https://github.com/Pankaj-k-Coder)                     |
|      3 | Sai Siva Sundar Jena | [SaiSiva0312](https://github.com/SaiSiva0312)                           |
|      4 | Abhishikta Mishra    | [abhishiktamishra04-coder](https://github.com/abhishiktamishra04-coder) |


---

⭐ If you find this project useful, feel free to explore the repository and its data quality analysis.
