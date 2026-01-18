# european-weightlifting-etl
Automated ETL pipeline extracting European Weightlifting Championships data (2019-2024) using Python, Regex, and Plotly.
# 🏋️ European Weightlifting ETL Pipeline

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458)
![Plotly](https://img.shields.io/badge/Plotly-Interactive%20Viz-3F4F75)
![Status](https://img.shields.io/badge/Status-Maintained-green)

## 📖 Project Overview

This project implements an automated **ETL (Extract, Transform, Load) pipeline** to analyze historical data from the **European Weightlifting Championships (2019-2024)**.

The primary objective is to transform unstructured data (complex HTML tables from Wikipedia) into a clean, unified analytical dataset. This enables the analysis of performance trends, country dominance, and gender equity gaps within the sport.

## 🚀 Key Features

* **🏗️ Modular ETL Architecture:** Refactored code following **DRY** (Don't Repeat Yourself) principles, allowing for easy scalability to include future championship years.
* **🧹 Advanced Data Cleaning:** Utilizes **Regular Expressions (Regex)** to robustly parse complex text strings (e.g., separating "Athlete Name + Country" from compound numerical results).
* **🛡️ Robust Error Handling:** Implements specific `try/except` logging mechanisms to ensure pipeline continuity by flagging corrupt records without halting execution.
* **📊 Interactive Visualization:** Generates dynamic dashboards using **Plotly** for Exploratory Data Analysis (EDA).

## 🛠️ Tech Stack

* **Language:** Python 3.9+
* **Extraction & Processing:** `Pandas`, `Lxml`, `Html5lib`, `Re` (Regex).
* **Visualization:** `Plotly Graph Objects`, `Kaleido` (for static image export).
* **Version Control:** Git & GitHub.

## ⚙️ Pipeline Workflow

1.  **Extract:** Iterates through a configuration dictionary (`YEAR_URLS`) to scrape multiple HTML tables from Wikipedia endpoints.
2.  **Transform:**
    * Standardizes column names across different years.
    * Extracts metadata (Gender, Weight Category) based on table indices.
    * Parses "dirty" cells to separate specific metrics: `Snatch`, `Clean & Jerk`, and `Total`.
    * Unifies data from 6 different years into a single DataFrame.
3.  **Load:** Exports the processed data into a unified CSV file: `processed_weightlifting_data_2019_2024.csv`.

## 📊 Results & Visualizations

### 1. Country Dominance (Top 10 Medal Count)
*Analysis of the total number of medals (Gold, Silver, Bronze) accumulated by country.*

![Medal Chart](chart_medallas.png)
*(Ensure the image chart_medallas.png is uploaded to your repository)*

### 2. Gender Equity Analysis
*Comparison of average performance and medal distribution between male and female categories.*

![Equity Chart](chart_equidad_medallas.png)

## 💻 Installation & Usage

Follow these steps to run the project locally:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/european-weightlifting-etl.git](https://github.com/YOUR_USERNAME/european-weightlifting-etl.git)
    cd european-weightlifting-etl
    ```

2.  **Create a virtual environment (Optional but recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Pipeline:**
    Open the notebook `etl_pipeline.ipynb` (or your renamed file) in Jupyter Notebook or VS Code and run all cells sequentially.

## 📂 Project Structure

```text
├── etl_pipeline.ipynb          # Main notebook containing the ETL logic
├── requirements.txt            # Project dependencies
├── .gitignore                  # Files ignored by Git
├── README.md                   # Project documentation
├── chart_medallas.png          # Visual output example
└── processed_data.csv          # Final generated dataset (optional)
