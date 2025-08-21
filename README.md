#  World Cup Data Engineering Project  

Welcome to the **World Cup Data Engineering Project**! 
This project focuses on **data cleaning, validation, and transformation** of FIFA World Cup match data, using Python and Google Colab.  
The goal is to turn raw historical match records into a **clean, analytics-ready dataset** for insights and reporting.  

---

##  Data Pipeline (Workflow)  

The workflow for this project follows a typical **data engineering process**:

1. **Raw Data (CSV)** → Import historical FIFA World Cup matches.  
2. **Data Cleaning** → Handle missing values, duplicates, and enforce constraints.  
3. **Validation** → Apply business rules:
   - No negative goals  
   - Half-time goals ≤ full-time goals  
   - Valid years (1930–2022)  
   - Unique `MatchID` values  
4. **Feature Engineering** → Add new insights:
   - Match results (winner/loser/draw)  
   - Tournament statistics per year  
   - Champion, runners-up, 3rd & 4th place teams  
5. **Output Dataset** → Generate a structured `WorldCup.csv` file for analytics.  

---

##  Project Overview  

This project demonstrates:  

- **Data Cleaning**: Remove duplicates, handle missing data, validate fields.  
- **Exploratory Data Analysis (EDA)**: Explore unique stages, winners, and team performances.  
-  **Data Transformation**: Aggregate stats (goals, attendance, matches, teams).  
-  **Business Rules Implementation**: Champions, runners-up, and placements per year.  
-  **Data Export**: Final clean dataset ready for BI tools, dashboards, or further analysis.  

 **Skills demonstrated**:  
- Python (Pandas, Matplotlib, Plotly)  
- Data Engineering (cleaning, validation, transformation)  
- Feature Engineering  
- Building analytics-ready datasets  

---

##  Repository Structure  

```
worldcup-data-engineering/
│
├── notebooks/                  # Original Colab notebook
│   └── Svetsko.ipynb
│
├── src/                        # Python script version
│   └── svetsko.py
│
├── data/                       # Input dataset (Matches.csv)
│
├── outputs/                    # Final cleaned dataset
│   └── WorldCup.csv
│
├── docs/                       # Documentation and diagrams
│
├── requirements.txt            # Python dependencies
├── README.md                   # Project overview and usage
└── .gitignore                  # Ignore unnecessary files
```

---

##  How to Run  

1. **Clone the repository**  
   ```bash
   git clone https://github.com/<username>/worldcup-data-engineering.git
   cd worldcup-data-engineering
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the notebook (Google Colab or Jupyter)**  
   ```bash
   jupyter notebook notebooks/Svetsko.ipynb
   ```

   **or execute the Python script**  
   ```bash
   python src/svetsko.py
   ```

---

##  Results  

The final dataset `WorldCup.csv` contains:  

- Year  
- Champion  
- Runners-up  
- Third & Fourth place teams  
- Number of qualified teams  
- Total goals scored  
- Number of matches played  
- Total attendance  

 Example insight: "Which country won the most World Cups?" or "How attendance evolved over time."  

---

##  Technologies  

- **Python**  
- **Pandas**  
- **Matplotlib & Plotly**  
- **Google Colab / Jupyter**  

---

##  License  

This project is licensed under the [MIT License](LICENSE).  

---

##  About  

This project was developed as a **data engineering portfolio project** to showcase:  
- Data cleaning and transformation  
- Application of data validation rules  
- Creation of analytics-ready datasets from raw historical data  
