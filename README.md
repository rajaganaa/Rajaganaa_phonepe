# PhonePe Pulse Data Visualization Dashboard

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Framework-Streamlit-red?logo=streamlit)
![MySQL](https://img.shields.io/badge/Database-MySQL-orange?logo=mysql)
![Plotly](https://img.shields.io/badge/Visualization-Plotly-green?logo=plotly)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success)

---

## 📊 Business Use Case

In the rapidly evolving landscape of digital payments in India, **understanding regional adoption and transaction trends is crucial for financial planning and policy-making**. This dashboard provides a comprehensive visualization of PhonePe's Pulse data, enabling stakeholders to:

- **Analyze Market Penetration**: Visualize user growth and transaction volumes across states and districts.
- **Identify Regional Trends**: Compare digital payment adoption between urban and rural areas.
- **Monitor Transaction Behavior**: Track the growth of different payment categories (e.g., Peer-to-Peer, Merchant Payments).
- **Strategic Decision Making**: Use data-driven insights to target under-penetrated markets and optimize infrastructure.

---

## 🏗️ Architecture

The system follows a robust **ETL (Extract, Transform, Load)** and **Visualization** pipeline:

```
┌─────────────────────────────────────────────────────────────┐
│                    PHONEPE PULSE DATA                        │
│             (Raw JSON Files from GitHub Repository)         │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│  ⚙️ DATA EXTRACTION & TRANSFORMATION ENGINE                  │
│  • Parsing: Recursive JSON file traversal                   │
│  • Cleaning: State name normalization & error handling      │
│  • Structuring: Conversion to Pandas DataFrames             │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│  🗄️ DATA WAREHOUSE (MySQL)                                  │
│  • Normalized Schema: 9 Relational Tables                   │
│  • Aggregated Tables: Insurance, Transaction, User          │
│  • Map Tables: District-level geospatial data               │
│  • Top Tables: Pincode-level granular data                  │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│  📈 INTERACTIVE DASHBOARD (Streamlit)                       │
│  • Geo-Visualization: Plotly Choropleth Maps                │
│  • Dynamic Filtering: Year, Quarter, and State selection    │
│  • Insight Generation: Bar Charts, Pie Charts, & Metrics    │
└─────────────────────────────────────────────────────────────┘
```

---

## ✨ Features

### 🗺️ **Geo-Spatial Analysis**
- **Interactive Choropleth Maps**: Visualize transaction intensity and user density across all Indian states.
- **District-Level Drill Down**: Hover over specific districts to see granular metrics like registered users and app opens.

### 📊 **Comprehensive Transaction Insights**
- **Category Analysis**: Breakdown of transactions by type (Recharge, Bill Payments, etc.).
- **Temporal Trends**: Analyze growth patterns over years and quarters.
- **Top Performers**: Identify top 10 states, districts, and pincodes by transaction volume and value.

### 👥 **User Demographics**
- **Device Analytics**: Understand user preference by mobile brand (Xiaomi, Samsung, Vivo, etc.).
- **Registration Growth**: Track the cumulative growth of registered users over time.

### 🗄️ **Robust Data Management**
- **Automated SQL Injection**: Seamlessly inserts processed data into a structured MySQL database.
- **Dynamic Data Loading**: Fetches live data from the database for real-time dashboard updates.

---

## 💻 Tech Stack

| Category | Technologies |
|----------|-------------|
| **Language** | Python 3.8+ |
| **Web Framework** | Streamlit, Streamlit Option Menu |
| **Database** | MySQL, mysql-connector-python |
| **Data Processing** | Pandas, NumPy, JSON, OS |
| **Visualization** | Plotly Express, PIL (Pillow) |
| **External APIs** | Requests (for GeoJSON data) |

---

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- MySQL Server installed and running locally
- pip package manager

### Setup Steps

1. **Clone the repository**:
   ```bash
   git clone git@github.com:rajaganaa/PhonePe-Transaction-Visualizer.git
   cd PhonePe-Transaction-Visualizer
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
   *Note: This will install streamlit, plotly, pandas, mysql-connector-python, and other required libraries.*

3. **Configure Database**:
   - Ensure your MySQL server is running.
   - The application will prompt for your MySQL password in the sidebar to establish a secure connection.
   - It automatically creates the `phonepee1` database and necessary tables.

4. **Prepare Data**:
   - Ensure the `data/` directory contains the PhonePe Pulse JSON files structured correctly (as per the `path` variables in `src/app.py`).

---

## 🚀 Usage

### Running the Dashboard

1. **Launch the Application**:
   ```bash
   streamlit run src/app.py
   ```

2. **Authenticate**:
   - Enter your MySQL root password in the sidebar input field.
   - The app will connect to the database and load the data.

3. **Explore Insights**:
   - **Home**: Overview of the project and technologies.
   - **Geo-Visualization**: Select Year and Quarter to view India maps.
   - **Analysis**: Dive deep into Transaction, User, and Insurance data with bar charts and top lists.

---

## 📝 License

This project is open-source and available for educational and portfolio purposes.

---

## 👤 Author

**Rajaganapathy M**  
GitHub: [@rajaganaa](https://github.com/rajaganaa)  
Email: rajaganaa@gmail.com

---

**Built with ❤️ for Data Science and Financial Analytics**
