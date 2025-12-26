# Real Estate Market Analysis - Madrid

## Project Overview

This project analyzes the real estate rental market in Madrid, highlighting investment opportunities through the analysis of Airbnb listing data. The goal is to identify profitable districts and neighborhoods by examining rental prices, occupancy rates, and estimated revenue.

The analysis is broken down into a data processing pipeline, ranging from data cleaning and preparation to in-depth exploratory analysis and final insights.

## Repository Structure

The project conforms to a data science workflow consisting of the following Jupyter Notebooks:

1.  **Data_preparation.ipynb**:
    -   **Objective**: Ingest, clean, and preprocess the raw data.
    -   **Key Steps**:
        -   Import raw data.
        -   Handle missing values and inconsistencies.
        -   Feature engineering: Creation of `total_price` (weighted revenue) and transformation of `availability_365` into `occupancy` metrics.
        -   Setup of the output database.

2.  **Creation_df.ipynb**:
    -   **Objective**: Finalize the datasets for analysis.
    -   **Key Steps**: Merging and formatting data frames for storage in the local SQLite database.

3.  **Tables_and_bbdd.ipynb**:
    -   **Objective**: Database management.
    -   **Key Steps**: Handling interactions with the `airbnb.db` SQLite database to store processed tables.

4.  **Analysis_and_insights.ipynb**:
    -   **Objective**: Core business analysis.
    -   **Key Steps**:
        -   Exploratory Data Analysis (EDA).
        -   Price distribution analysis by district and neighborhood.
        -   Occupancy rate evaluation.
        -   Revenue estimation (`total_price` vs. `price`).
        -   Identification of market clusters (Low-Low, Medium-Medium, High-High).

5.  **Results.ipynb**:
    -   **Objective**: Summary of findings.
    -   **Key Steps**: Presentation of the final conclusions and strategic recommendations based on the data.

## Key Insights

-   **Pricing Correlation**: There is a direct but nuanced correlation between rental price and total revenue.
-   **Neighborhood Segmentation**: The market clearly segments into distinct clusters based on pricing power and demand, with districts like *Salamanca* and *Centro* showing different profiles compared to peripheral areas.
-   **Revenue Drivers**: Revenue is not solely dependent on high nightly rates; occupancy plays a crucial role.

## Technical Requirements

This project requires **Python 3.x** and the following libraries:

-   **Data Manipulation**: `pandas`, `numpy`
-   **Visualization**: `matplotlib`, `seaborn`
-   **Database**: `sqlalchemy`

### Installation

Ensure you have a Python environment set up. You can install the dependencies using pip:

```bash
pip install pandas numpy matplotlib seaborn sqlalchemy
```

*Note: Since this project uses Jupyter Notebooks, ensure `jupyter` or `jupyterlab` is also installed.*

## Usage Instructions

1.  **Clone the repository** (if applicable) or navigate to the project folder.
2.  **Run the Notebooks** in the following logical order to reproduce the analysis:
    1.  `Data_preparation.ipynb`
    2.  `Creation_df.ipynb` (if separate from prep)
    3.  `Analysis_and_insights.ipynb`
    4.  `Results.ipynb`
3.  **Database**: The project utilizes a local SQLite database file `DatosCaso1/airbnb.db`. Ensure this path exists or update the connection strings in the notebooks if moving files.

## Data Source

The data is based on Airbnb listings for Madrid. The analysis identifies key variables such as:
-   `neighbourhood_group` (District)
-   `neighbourhood` (Neighborhood)
-   `price` (Nightly rate)
-   `room_type` (Entire home, Private room, etc.)
