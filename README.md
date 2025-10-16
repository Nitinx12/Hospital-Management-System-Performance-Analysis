# Hospital Management - Data Analysis Project

## Introduction & Objective

This project provides a comprehensive exploratory data analysis (EDA) of a hospital management system. The primary objective is to analyze the operational and financial performance of the hospital to identify key trends, uncover actionable insights, and provide data-driven recommendations for growth and efficiency.

The analysis is driven by 16 specific business questions, exploring patient demographics, appointment statistics, revenue, and doctor performance.

***

## 📊 Key Analyses & Features

This project answers critical business questions through advanced SQL queries and visual analysis. Key areas of investigation include:

* **Patient Demographics:**
    * Distribution of patients by age group and gender.
    * [cite_start]Analysis of new patient registrations per month[cite: 17].
    * [cite_start]Breakdown of patients by insurance provider[cite: 20].

* **Appointment & Specialization Analysis:**
    * [cite_start]Total count of appointments by status ('Completed', 'Scheduled', 'Cancelled', 'No-show')[cite: 17].
    * [cite_start]Identification of the busiest months and days of the week for appointments[cite: 17].
    * [cite_start]Distribution of appointments across different medical specializations (e.g., Pediatrics, Dermatology)[cite: 19].
    * [cite_start]Most common reasons for patient visits (e.g., Checkup, Consultation)[cite: 17].

* **Revenue & Financial Performance:**
    * [cite_start]Total amount billed for each payment method, broken down by payment status ('Paid', 'Unpaid')[cite: 18].
    * [cite_start]Identification of the top 5 doctors generating the most revenue[cite: 18, 19].
    * [cite_start]Calculation of month-over-month percentage growth in revenue[cite: 18].
    * 3-month moving average for monthly revenue.

* **Advanced Patient & Doctor Analytics:**
    * [cite_start]Ranking of doctors within each hospital branch based on revenue generated[cite: 18, 19].
    * [cite_start]Average number of days between consecutive patient appointments[cite: 17].
    * [cite_start]Identification of patients who have visited multiple specializations[cite: 17, 19].
    * [cite_start]Querying billing records for patients who were billed on consecutive days[cite: 18].

***

## 🛠️ Tech Stack & Tools

* **Database:** PostgreSQL
* **Language:** Python, SQL
* **Data Loading & Manipulation:** Pandas, SQLAlchemy
* **Querying & Analysis:** DuckDB, SQL (using CTEs, Window Functions, and advanced aggregations)
* **Data Visualization:** Matplotlib, Seaborn
* **Environment:** Jupyter Notebook

***

## 🚀 How to Run This Project

1.  **Prerequisites:**
    * Ensure you have Python and PostgreSQL installed on your system.
    * Install the required Python libraries:
        ```bash
        pip install pandas sqlalchemy duckdb matplotlib seaborn
        ```

2.  **Database Setup:**
    * Create a new PostgreSQL database (e.g., `managementdata`).
    * Update the connection string in the `Load_data_into_PostgreSQL.py` file with your PostgreSQL credentials.
    * Run the script to load the `.csv` data files into your database:
        ```bash
        python Load_data_into_PostgreSQL.py
        ```

3.  **Run the Analysis:**
    * **SQL Analysis:** Execute the queries in the `HMS project FOR SQL.sql` file using a SQL client of your choice (like DBeaver, pgAdmin, or VS Code).
    * **Python & Visualization:** Open and run the `Hospital_notebook.ipynb` file in a Jupyter environment to see the full exploratory data analysis and visualizations.

***

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

## 📬 Contact

Feel free to reach out with any questions or feedback!

* **Nitin K.**
* **LinkedIn:** [https://www.linkedin.com/in/nitin-k-220651351/](https://www.linkedin.com/in/nitin-k-220651351/)
* **GitHub:** [https://github.com/Nitinx12](https://github.com/Nitinx12)
* **Email:** [nitin321x@gmail.com](mailto:nitin321x@gmail.com)
