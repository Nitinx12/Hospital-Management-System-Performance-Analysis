# Hospital Management System Performance Analysis
*Leveraging SQL and Python to derive insights for operational efficiency and financial growth.*

---

## 📋 Table of Contents
* [Project Overview](#-project-overview)
* [Business Objective](#-business-objective)
* [Dataset](#-dataset)
* [Tech Stack](#-tech-stack)
* [Methodology](#-methodology)
* [Results and Key Findings](#-results-and-key-findings)
* [Visualizations](#-visualizations)
* [Conclusion & Recommendations](#-conclusion--recommendations)
* [Installation & Usage](#-installation--usage)
* [Repository Structure](#-repository-structure)
* [Contact Information](#-contact-information)

---

## 📝 Project Overview
This project presents an in-depth analysis of a hospital management system's operational and financial data. By leveraging both SQL for complex querying and Python for exploratory data analysis (EDA), the goal was to uncover key trends, identify performance bottlenecks, and provide actionable, data-driven recommendations to enhance efficiency and drive growth.

---

## 🎯 Business Objective
The primary objective was to analyze the clinic's performance from multiple perspectives—patient demographics, appointment logistics, doctor workload, and financial health. The analysis sought to answer critical business questions, including:
* What is the demographic profile of our patients (age, gender)?
* Which medical specializations and doctors are most in-demand?
* What are the patterns in appointment scheduling, statuses (Completed, No-show), and reasons for visits?
* What is the financial performance in terms of revenue, billing status, and insurance providers?
* How can we reduce no-shows, balance doctor workload, and increase revenue?

---

## 🗃️ Dataset
The analysis was performed on a simulated dataset representing a typical hospital management system. The data is structured across five main tables:

| Table          | Key Columns                                                                |
| :------------- | :------------------------------------------------------------------------- |
| **patients** | `patient_id`, `first_name`, `gender`, `date_of_birth`, `insurance_provider`  |
| **doctors** | `doctor_id`, `first_name`, `specialization`, `years_experience`, `hospital_branch` |
| **appointments** | `appointment_id`, `patient_id`, `doctor_id`, `appointment_date`, `status`    |
| **treatments** | `treatment_id`, `appointment_id`, `treatment_type`, `cost`                 |
| **billing** | `bill_id`, `patient_id`, `treatment_id`, `amount`, `payment_status`          |

---

## 🛠️ Tech Stack
* **Database:** PostgreSQL
* **Language:** Python, SQL
* **Libraries:**
    * **Python:** Pandas, NumPy, Matplotlib, Seaborn, DuckDB, SQLAlchemy
    * **SQL:** PostgreSQL queries for aggregation, window functions (LAG, DENSE_RANK), CTEs, and joins.

---

## 🔬 Methodology

#### 1. Data Loading and Validation
The raw `.csv` files were loaded into a PostgreSQL database using a Python script with the SQLAlchemy library. Initial data validation was performed to ensure data integrity and correct data types.

#### 2. SQL Querying for Business Insights
A series of 16 SQL queries were executed to answer specific business questions. These queries involved complex joins, Common Table Expressions (CTEs), window functions like `LAG()` and `DENSE_RANK()`, and aggregations to calculate metrics such as revenue, patient counts, and appointment statistics.

#### 3. Exploratory Data Analysis (EDA) with Python
The `Hospital_notebook.ipynb` Jupyter Notebook was used for a deeper visual analysis. Key steps included:
* **Data Cleaning:** Converted date/time columns to the correct `datetime` format and checked for null values across all datasets.
* **Univariate Analysis:** Analyzed distributions of key variables like patient age, gender, and appointment statuses using histograms and pie charts.
* **Bivariate Analysis:** Explored relationships between variables, such as doctor's experience vs. the number of appointments they handle, using scatter plots.
* **Trend Analysis:** Visualized monthly trends for new patient registrations and total appointments using line charts.

---

## 📊 Results and Key Findings
The analysis yielded several critical insights into the clinic's operations:

* **High No-Show/Cancellation Rate:** A significant number of appointments result in "No-shows" (52) or are "Cancelled" (51). Completed appointments (46) are the least frequent status, indicating a major opportunity to improve patient follow-through.
* **Billing Inefficiencies:** The combined number of "Pending" (69) and "Failed" (67) bills is more than double the number of "Paid" bills (64), pointing to a critical bottleneck in the revenue collection process.
* **Demographic Concentration:** The majority of patients are young adults between 25-35 years old. There is also a moderate gender imbalance, with male patients (62%) outnumbering female patients (38%).
* **Specialization Imbalance:** Pediatrics is the most popular specialization, accounting for 49% of all appointments, followed by Dermatology (35%). This suggests an uneven demand for services.
* **Uneven Doctor Workload:** Dr. Sarah Taylor handles a significantly higher number of appointments (29) compared to her colleagues, indicating a potential for burnout and an opportunity to distribute workload more evenly.

---

## 📈 Visualizations

* **Age Distribution of Patients (Histogram):** Revealed that the largest patient group is aged 25-35.
    `![Patient Age Distribution](images/age_distribution.png)`
* **Appointment Status Distribution (Bar Chart):** Clearly showed the high volume of 'No-Show' and 'Cancelled' appointments compared to 'Completed' ones.
    `![Appointment Status](images/appointment_status.png)`
* **Appointments by Specialization (Pie Chart):** Highlighted the dominance of Pediatrics in the clinic's services.
    `![Appointments by Specialization](images/specialization_pie.png)`
* **Revenue per Month (Bar Chart):** Displayed significant revenue fluctuations, with a notable peak in June and a sharp dip in February.
    `![Monthly Revenue](images/monthly_revenue.png)`

---

## 💡 Conclusion & Recommendations

The analysis indicates that while the clinic shows positive growth in new patient registrations, there are significant operational and financial areas needing improvement.

**Recommendations:**
1.  **Reduce No-Shows:** Implement an automated SMS/email reminder system and introduce a cancellation policy to discourage last-minute changes and no-shows.
2.  **Overhaul Billing Process:** Dedicate resources to follow up on pending insurance claims and failed payments immediately. Investigate the root cause of failed transactions and consider offering discounts for upfront payments.
3.  **Balance Doctor Workload:** Use a more intelligent scheduling system to distribute appointments evenly. Promote the expertise of less-booked doctors to balance patient flow.
4.  **Expand High-Demand & Targeted Services:** Invest in expanding the popular Pediatrics and Dermatology departments. At the same time, launch targeted marketing campaigns for women's health to address the gender gap in the patient base.

---

## ⚙️ Installation & Usage
To replicate this analysis, follow these steps:

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/Nitinx12/Hospital-Management-System-Analysis.git](https://github.com/Nitinx12/Hospital-Management-System-Analysis.git)
    cd Hospital-Management-System-Analysis
    ```
2.  **Set Up PostgreSQL Database:**
    * Ensure you have PostgreSQL installed.
    * Create a new database (e.g., `managementdata`).
    * Update the connection string in the `Load_data_into_PostgreSQL.py` file with your database credentials.
3.  **Load Data:**
    * Place the five `.csv` files (`appointments.csv`, `billing.csv`, etc.) in the `data/` directory.
    * Run the Python script to load the data into your PostgreSQL database:
        ```bash
        python Load_data_into_PostgreSQL.py
        ```
4.  **Run Analysis:**
    * **For SQL Analysis:** Execute the queries in `HMS project FOR SQL.sql` using a SQL client like DBeaver or `psql`.
    * **For Python EDA:** Open and run the `Hospital_notebook.ipynb` Jupyter Notebook. Ensure you have the required libraries installed (`pip install pandas sqlalchemy notebook seaborn matplotlib duckdb`).

## 📂 File Structure

```
├── Hospital_notebook.ipynb         # Jupyter Notebook with Python-based EDA and visualizations.
├── HMS project FOR SQL.sql         # Contains all 16 advanced SQL queries for analysis.
├── Load_data_into_PostgreSQL.py    # Python script to load CSV data into PostgreSQL.
├── Questions for hospital.pdf      # The list of 16 business questions driving the analysis.
├── appointments.csv                # Raw data file.
├── billing.csv                     # Raw data file.
├── doctors.csv                     # Raw data file.
├── patients.csv                    # Raw data file.
├── treatments.csv                  # Raw data file.
└── README.md                       # You are here!
```

***
  
## 📞 Contact Information
* **Nitin Kumar Sharma**
* **LinkedIn:** [https://www.linkedin.com/in/nitin-k-220651351/](https://www.linkedin.com/in/nitin-k-220651351/)
* **GitHub:** [https://github.com/Nitinx12](https://github.com/Nitinx12)
* **Email:** Nitin321x@gmail.com
