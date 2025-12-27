# Real Estate Market Analysis - Madrid 🇪🇸

## 📊 Executive Summary

This project presents a data-driven investment strategy for the Madrid real estate market, specifically focusing on the short-term tourist rental sector (Airbnb). By analyzing public rental data, we identify specific property profiles and geographical areas that offer the highest commercial potential and return on investment (ROI).

The analysis reveals that profitability is driven not just by high nightly rates but by a balance of acquisition cost and consistent occupancy. We have pinpointed **10 specific neighborhoods** that outperform the market.

## 🎯 Strategic Recommendations

Based on the data analysis, the valuation team should focus on the following investment opportunities:

### 1. Optimal Property Profile
*   **Capacity**: Properties capable of accommodating **3 guests** maximize the purchase-price-to-revenue ratio.
*   **Location Strategy**: Proximity to major tourist "points of interest" is **not** a primary driver of rental price in the identified top-tier neighborhoods. Therefore, we recommend acquiring lower-cost properties within these high-demand districts, even if they are not centrally located next to landmarks.

### 2. Top Investment Neighborhoods
We have segmented the 10 best-performing neighborhoods into four investment tiers:

*   **💎 High Investment**:
    *   *Recoletos*
*   **📈 Medium-High Investment**:
    *   *Niño Jesús*
    *   *El Viso*
*   **⚖️ Medium Investment**:
    *   *Argüelles*
    *   *Costillares*
    *   *El Goloso*
*   **💰 Low Investment (Entry Level)**:
    *   *Rosas*
    *   *Simancas*
    *   *Comillas*
    *   *Los Rosales*

---

## 📈 Analysis Insights & Visualizations

### Market Clusters
Our analysis shows a strong correlation between district purchase prices and potential revenue, clustering into distinct market segments:
*   **High-High**: High entry cost, high revenue (e.g., *Centro*, *Salamanca*).
*   **Medium-Medium**: Balanced risk/reward.
*   **Low-Low**: Lower entry barrier, moderate revenue.

---

## 🛠️ Repository Structure

The project follows a structured data science pipeline implemented in Jupyter Notebooks:

### 1. Data Cleaning & Preparation
*   **`03_Data_preparation.ipynb`**:
    *   Ingests raw Airbnb data.
    *   Cleanses missing values and inconsistent records.
    *   **Feature Engineering**:
        *   `occupancy`: Transformed from availability data (365 days).
        *   `total_price`: Weighted revenue metric adjusting for occupancy rates.

### 2. Database Management
*   **`01_Tables_and_bbdd.ipynb`** & **`02_Creation_df.ipynb`**:
    *   Manages the local SQLite database (`airbnb.db`) for storing processed tables.
    *   Formats and merges datasets for analysis.

### 3. Exploratory Data Analysis (EDA)
*   **`04_Analysis_and_insights.ipynb`**:
    *   In-depth analysis of rental prices, occupancy rates, and property characteristics.
    *   Clustering of districts and neighborhoods.
    *   Revenue estimation modeling.

### 4. Final Conclusions
*   **`05_Results.ipynb`**:
    *   Synthesizes all findings into actionable business recommendations.
    *   Defining the "Golden List" of neighborhoods.

---

## 💻 Technichal Setup

### Prerequisites
*   **Python 3.x**
*   **Jupyter Lab / Notebook**

### Key Libraries
*   `pandas` & `numpy`: Data manipulation.
*   `matplotlib` & `seaborn`: Data visualization.
*   `sqlalchemy`: Database interaction.

To install dependencies:
```bash
pip install pandas numpy matplotlib seaborn sqlalchemy
```

### How to Run
1.  Ensure the SQLite database file `DatosCaso1/airbnb.db` is available (or re-run prep notebooks to generate it).
2.  Execute the notebooks in numerical order (`01` to `05`) to replicate the full analysis pipeline.

---

## 📂 Data Sources
The analysis exploits public Airbnb listings data for the city of Madrid, focusing on variables such as:
*   `neighbourhood_group` (District) & `neighbourhood` (Barrio)
*   `price` (Nightly rate)
*   `room_type` (Entire home, Private room, etc.)
*   `availability_365` (Proxy for occupancy)
