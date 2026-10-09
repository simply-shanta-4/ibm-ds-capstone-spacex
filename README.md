# SpaceX Falcon 9 First Stage Landing Prediction

IBM Data Science Professional Certificate: Applied Data Science Capstone

## Overview

SpaceX advertises Falcon 9 launches at about **$62M**, versus **$165M+** from other providers. Most of the savings come from reusing the first stage, so whether the first stage lands largely determines the cost of a launch.

This project collects and analyses Falcon 9 launch data, then trains classification models to **predict whether the first stage will land successfully**. The prediction can be used to estimate launch cost, for example by a competitor bidding against SpaceX for a contract.

## Questions we set out to answer

1. Which factors (payload, orbit, launch site, booster) drive a successful landing?
2. Does landing success improve over time as flights accumulate?
3. How do the launch sites differ in outcomes and location?
4. Which classification model predicts landing success best?

## Methodology

1. **Data collection**: SpaceX REST API and Wikipedia web scraping
2. **Data wrangling**: handle missing values and create the landing label (`Class`)
3. **EDA**: Matplotlib / Seaborn charts and SQL queries
4. **Interactive analytics**: Folium launch-site map and Plotly Dash dashboard
5. **Predictive analysis**: Logistic Regression, SVM, Decision Tree and KNN tuned with GridSearchCV

## Repository contents

| Stage | Notebook / file |
| --- | --- |
| Data collection (API) | [jupyter-labs-spacex-data-collection-api-v2-completed.ipynb](jupyter-labs-spacex-data-collection-api-v2-completed.ipynb) |
| Data collection (web scraping) | [jupyter-labs-webscraping-completed.ipynb](jupyter-labs-webscraping-completed.ipynb) |
| Data wrangling | [labs-jupyter-spacex-Data_wrangling-v2-completed.ipynb](labs-jupyter-spacex-Data_wrangling-v2-completed.ipynb) |
| EDA with data visualization | [jupyter-labs-eda-dataviz-v2-completed.ipynb](jupyter-labs-eda-dataviz-v2-completed.ipynb) |
| EDA with SQL | [jupyter-labs-eda-sql-coursera_sqllite-completed.ipynb](jupyter-labs-eda-sql-coursera_sqllite-completed.ipynb) |
| Interactive map (Folium) | [lab-jupyter-launch-site-location-v2-completed.ipynb](lab-jupyter-launch-site-location-v2-completed.ipynb) |
| Dashboard (Plotly Dash) | [spacex_dash_app.py](spacex_dash_app.py) |
| Predictive analysis | [SpaceX-Machine-Learning-Prediction-Part-5-v1-completed.ipynb](SpaceX-Machine-Learning-Prediction-Part-5-v1-completed.ipynb) |

The notebooks are meant to be read in the order shown. Each one produces data used by the next (for example `dataset_part_1.csv`, then `dataset_part_2.csv`, then `dataset_part_3.csv`).

## Key findings

- **Landing success rose from 0% (2010 to 2013) to about 90% (2019)** as flights and reuse experience accumulated.
- **KSC LC-39A has the best success ratio** (about 77%, 10 of 13 launches); every site is close to the coast and away from cities.
- **Orbits ES-L1, GEO, HEO and SSO reached 100% success**; mid-range payloads (about 2 to 5.5 tonnes) land most often.
- **All four tuned models reach about 83% test accuracy** (15 of 18 test launches). The Decision Tree has the best cross-validation accuracy (about 87.5%).
- The best model made **no false negatives**: every successful landing was predicted correctly. All 3 errors were failed landings predicted as successful.

## Tech stack

Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn, BeautifulSoup, requests, SQLite, Folium, Plotly Dash

## How to run

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR-USERNAME/ibm-ds-capstone-spacex.git
   cd ibm-ds-capstone-spacex
   ```

2. Install the dependencies:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn beautifulsoup4 requests folium plotly dash ipython-sql
   ```

3. Open the notebooks in Jupyter and run them in the order shown in the table above.

4. To launch the dashboard:

   ```bash
   python spacex_dash_app.py
   ```

   Then open http://127.0.0.1:8050 in your browser.

## Author

Ayush
