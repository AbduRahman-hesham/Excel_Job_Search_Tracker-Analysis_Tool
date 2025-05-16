 # 📊 Excel Job Search Tracker

![Dashboard GIF](https://github.com/user-attachments/assets/0e038d96-5ef8-483f-80c2-3bae52e3d70d)



## 📘 Introduction


This interactive dashboard is designed to empower job seekers in the data industry by helping them explore salary benchmarks for their desired roles. Whether you're negotiating an offer or planning your next career move, this tool offers valuable insights into market trends.

The dataset was collected from multiple online sources and contains real job listings compiled over the span of a year. It reflects genuine data industry roles, offering an accurate snapshot of the job market—complete with salaries, locations, and required skills.

### 📁 Dashboard File

You can explore the final dashboard here: 
[Job_search Excel Project.xlsx](https://github.com/user-attachments/files/20258175/Job_search.Excel.Project.xlsx)
---

## 🧠 Excel Skills Demonstrated

This project leverages core Excel capabilities to deliver powerful analytics:

- **📉 Charts** – For dynamic and visual representation of key metrics  
- **🧮 Formulas & Functions** – To extract, calculate, and analyze trends  
- **❎ Data Validation** – Ensures clean inputs and consistent results  

---

## 📊 Dataset Overview

The project uses real-world job listings in the data field from 2023. The dataset includes:

- 👨‍💼 **Job Titles**
- 💰 **Salaries (Annual & Hourly)**
- 📍 **Locations**
- 🛠️ **Key Technical Skills**

---

## 🛠️ Dashboard Build

### 📉 Salary by Role – Bar Chart

![salary](https://github.com/user-attachments/assets/0d6d40a1-5af0-4c51-a6db-edb57731898c)

- **Excel Features:** Horizontal bar chart with formatted salary labels
- **Design Focus:** Sorted by descending salary for quick comparison  
- **Insight:** Senior roles and engineering jobs offer the highest pay

### 🌍 Global Salary Overview – Map Chart

![geo](https://github.com/user-attachments/assets/5aaae878-da84-4df0-88ca-d255af422ed1)

- **Excel Features:** Map chart to visualize global salary variations  
- **Design Focus:** Color-coded regions highlight disparities  
- **Insight:** Geographic patterns in compensation become immediately clear  

---

## 🧮 Key Formulas

### 💰 Median Salary by Role & Region

```excel
=MEDIAN(
  IF(
    (Table2[job_title_short]=$A2)*
    (ISNUMBER(Table2[salary]))*
    (Table2[salary]<>0)*
    (country=Table2[job_country])*
    (ISNUMBER(
             SEARCH(
                    type,Table2[job_schedule_type])
     )
     ),Table2[salary]))

```

- **Purpose:** Computes median salary using multiple filters (title, country, type)
- **Usage:** Powers the salary comparison table in the dashboard

🍽️ **Background Table**

![xlookup](https://github.com/user-attachments/assets/5f7074d6-5595-40b5-b7da-cc6cf6d4fddc)


📉 **Dashboard View**

![salary dashboard](https://github.com/user-attachments/assets/8dc6ea22-b12d-46ed-887f-ffbbd1e4e2cc)

### ⏰ Job Schedule Type Filter

```excel
=FILTER(
     A1#,
     NOT(
       ISNUMBER(
            SEARCH("and",A1#)
       )
     )*
     (A1#<>0)
)
```

```
=COUNTIFS(
     Table2[job_schedule_type],"*" &B1& "*",
     Table2[job_title_short],title,
     Table2[job_country],country
)

```
- **Purpose:** Generates a clean, unique list of job schedule types  
- **Use Case:** Populates a validated dropdown for job type selection  

🍽️ **Background Table && Dashboard View**

![jop_type](https://github.com/user-attachments/assets/4e3ed9ac-627b-4306-8698-02fabd0bbb45)
---

## ✅ Data Validation

- **Application:** Data validation was used to restrict input in filters (e.g., Job Title, Country, Type)
- **Benefits:**
  - 🚫 Prevents errors
  - 🎯 Keeps user selections consistent
  - 🧭 Improves dashboard navigation


---

## 🏁 Conclusion

This dashboard brings salary insights to life using real job data and core Excel tools. It’s a practical example of how data professionals can use Excel not just for calculations, but for storytelling, decision-making, and career planning.

Explore how roles, locations, and job types shape compensation, and use this tool to take charge of your career direction.

