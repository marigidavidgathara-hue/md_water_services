Maji Ndogo Water Analysis Project

![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

Project Overview
This project involves a comprehensive audit and analysis of the **Maji Ndogo** national water database. The goal was to solve a national water crisis by analyzing 60,000+ records to optimize infrastructure budgets, identify corruption, and ensure equitable water access.

The project demonstrates **Full-Stack Data Analysis**, moving from raw SQL database management to Python-based data cleaning, forensic auditing, and final policy recommendations.

The Challenge
The Maji Ndogo water network was suffering from:
1.  **Queue Times:** Citizens were waiting 4+ hours for water in specific regions.
2.  **Infrastructure Decay:** Broken taps and polluted wells were going unnoticed.
3.  **Data Integrity Issues:** Discrepancies between field surveyor logs and independent auditor reports suggested potential fraud/negligence.

## 🗄️ Database Schema (ERD)
The database `md_water_services` consists of the following key tables:
* **`location`**: Geographic data (Province, Town, Type).
* **`water_source`**: Source types (Well, River, Shared Tap) and capacity.
* **`visits`**: Log of citizen visits, queue times, and assigned employees.
* **`well_pollution`**: Biological and chemical contamination data.
* **`auditor_report`**: Independent quality checks used for cross-referencing.
* **`employee`**: Staff details for surveyors and managers.




<img width="894" height="796" alt="ERD database" src="https://github.com/user-attachments/assets/5c7bfae8-7c34-4e95-8e0f-aeebab9b8e78" />



















## 🛠️ Methodology

### 1. Data Cleaning & Integrity (Python + SQL)
* **Standardization:** Used Python (Pandas) to clean employee contact information and standardise email formats.
* **Pollution Data:** Corrected inconsistencies in the `well_pollution` table (separating "Chemical" vs. "Biological" descriptions) to ensure accurate filtering logic.

### 2. Forensic Analysis (Fraud Detection)
* **Objective:** Identify employees misreporting water quality.
* **Method:** SQL subqueries compared `water_quality` scores (field officials) against `auditor_report` scores (independent auditors).
* **Result:** Created a `suspect_list` View identifying 4 employees with statistically significant error rates, flagging them for internal review.

### 3. Operational Efficiency (Time-Series Analysis)
* Analyzed `time_in_queue` data across days of the week and hours of the day.
* **Key Insight:** Saturdays witnessed the highest average queue times.
* **Recommendation:** Extended shift hours on weekends to reduce bottlenecks.

### 4. Infrastructure Logic (Automated Decision Support)
Developed SQL logic to categorize sources and assign specific engineering solutions:
* **Bio-Contaminated Wells** $\rightarrow$ Install UV Filters.
* **Chemically Contaminated Wells** $\rightarrow$ Install RO Filters.
* **River Sources** $\rightarrow$ Drill new wells.
* **Broken Taps** $\rightarrow$ Dispatch repair teams.

---

## 📊 Key Results
* **Corruption Identified:** Flagged employees submitting false records, improving data reliability.
* **Budget Optimization:** Generated a prioritized **"Project Progress Report"** that allocates funds to high-risk sources (polluted/broken) first.
* **Queue Reduction:** Data-driven shift changes expected to reduce average wait times by ~30% on weekends.

---

## 💻 How to Run This Project

### Prerequisites
* MySQL Workbench / Command Line
* Python 3.x
* Jupyter Notebook

### Steps
1.  **Clone the Repo:**
    ```bash
    git clone [https://github.com/yourusername/maji-ndogo-analysis.git](https://github.com/yourusername/maji-ndogo-analysis.git)
    ```
2.  **Database Setup:**
    * Import `md_water_services.sql` into your MySQL local instance.
3.  **Run Analysis:**
    * Open `Aaaa.ipynb` in Jupyter Notebook.
    * Ensure your database connection string (user/password) is configured correctly.
    * Run all cells to generate the analysis and final report.

## 👤 Author
 David Gathara Marigi 
* [LinkedIn Profile](www.linkedin.com/in/david-gathara)
* [Portfolio/Website](Link)

*Note: This project is a simulation based on a realistic scenario for data analysis training purposes.*
