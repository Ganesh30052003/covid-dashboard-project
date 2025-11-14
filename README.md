# 🦠 COVID-19 Analytics Dashboard (2020–2025) – Power BI  

An interactive **multi-page Power BI dashboard** analyzing the global COVID-19 pandemic with insights into **cases, deaths, vaccination progress, and country-wise patterns**.  
This project uses the **OWID (Our World In Data)** global COVID dataset and demonstrates **end-to-end data analytics workflow**: cleaning, modeling, DAX, visualization, and deployment.

---

## ⭐ Project Overview  
This project focuses on understanding how COVID-19 evolved from **2020 to 2025** globally and across individual countries.

It answers key analytical questions:

- 📌 How did cases and deaths grow across the world?  
- 📌 Which countries were most impacted?  
- 📌 How did vaccination roll out globally?  
- 📌 What was the effect of government restrictions?  
- 📌 How do continents compare in vaccination performance?  

The final dashboard consists of **three interactive pages**.

---

## 📊 Dashboard Pages

### **📌 Page 1 — Global COVID-19 Summary**
- Total cases, total deaths, CFR%, vaccination rate  
- New cases trend (7-day rolling average)  
- New deaths trend  
- Global map of total cases (latest snapshot)  
- Top 10 countries by total cases  
- Filters: continent, country, date  

---

### **📌 Page 2 — Country-Level Analysis**
- Country-specific total cases, deaths, CFR%, vaccination rate  
- Daily new case & death trends  
- Vaccination progress (country timeline)  
- Government stringency index (lockdown & response levels)  
- Country slicer  

---

### **📌 Page 3 — Vaccination Insights**
- Total vaccinations  
- People vaccinated (1 dose)  
- Fully vaccinated population  
- Booster dose analysis  
- Global vaccination progress (line chart)  
- Continent-wise vaccination rate  
- Top 10 vaccinated countries  

---

## 🗂 Files in This Repository

| File | Description |
|------|-------------|
| `covid_dashboard.pbix` | Complete Power BI dashboard (3 pages) |
| `owid-covid-data.csv` | Cleaned dataset used for the dashboard |
| `README.md` | Documentation for the project |

---

## 🛠 Tools & Technologies Used

- **Power BI Desktop**
- **Power Query**
- **DAX (Data Analysis Expressions)**
- **Data Modeling (Star Schema)**
- **Interactive Visualizations**
- **GitHub Version Control**
- **Web Embedding / Deployment**

---

## 🔍 Key DAX Measures

Some important measures used:

```DAX
Total Cases = SUM(OWID[total_cases])

New Cases (7-day Avg) =
AVERAGEX(
    DATESINPERIOD(DateTable[Date], MAX(DateTable[Date]), -7, DAY),
    [New Cases]
)

Latest Total Cases (By Country) =
VAR LatestDate =
    CALCULATE(MAX(OWID[date]), ALLEXCEPT(OWID, OWID[country]))
RETURN
    CALCULATE(MAX(OWID[total_cases]), OWID[date] = LatestDate)

Country Vaccination Rate (%) =
DIVIDE(
    SUM(OWID[people_fully_vaccinated]),
    SUM(OWID[population])
) * 100
```

---

## 🌍 Data Source  
Dataset provided by:  
**Our World In Data (OWID)**  
🔗 https://ourworldindata.org/coronavirus

Dataset covers:
- Cases & deaths  
- Population data  
- Vaccination metrics  
- Testing  
- Government stringency index  
- Demographic details  

---

## 🚀 Live Dashboard  
[Live COVID-19 Dashboard]([https://yourwebsite.com](https://app.powerbi.com/reportEmbed?reportId=68651998-e15d-4739-ba6d-e81500d55348&autoAuth=true&ctid=9de30af8-810d-424e-9a84-5f0c1348e7c6))


## 🤝 Contribution Guidelines (Open Source Friendly)

We welcome contributions!

How to contribute:
1. Fork this repo  
2. Create a new branch  
3. Commit improvements  
4. Open a Pull Request  

You may contribute:
- Better visuals  
- New DAX measures  
- More pages  
- Bug fixes  
- Documentation improvements  

---

## 📬 Contact  

**Developer:** Ganesh Kondamwar  
Feel free to connect or ask questions!  

---

## ⭐ Support  
If you like this project, PLEASE ⭐ **star this repository**.  
Your support makes open-source better!

