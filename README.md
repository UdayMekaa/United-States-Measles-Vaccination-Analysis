# *Measles Vaccination Rates in Schools across united States🇺🇸*
### *1. Introduction:*
*This project explores school-level measles vaccination rates across multiple U.S. states, using historical data to uncover patterns and predict missing values. The aim is to support public health decision-making by identifying key factors linked to higher or lower vaccination coverage.*

***Data Source:*** *All-measles-rates dataset (multiple states, multiple school types).
Key Variables:*

* overall – overall vaccination rate for the school

* mmr – MMR vaccination rate

* xper, xmed, xrel – exemption rates (personal, medical, religious)

* type – school type (public, private, charter, etc.)

* state, enroll – location and enrollment size

### *2. Data Preparation*
* Removed rows with missing target (overall) for modeling.

* Encoded categorical features (state, type) using one-hot encoding.

* Imputed missing numeric values with median imputation.

* Final dataset for modeling: 12,252 rows, 15 features.

### *3. Exploratory Data Analysis (EDA)* \
***School Type Differences:***

| School Type | Avg Overall Rate | Avg MMR Rate |
|:--------|:-----:|------:|
| Kindergarten  | 87.8%  | 94.3%    |
| Public   | 23.0%  | 58.7%    |
| Private | 55.1%   | 40.4%    |

* Kindergarten schools have the highest rates overall.

* Private schools show the lowest coverage, especially for MMR.

***State Differences (ANOVA):***

* F-statistic for overall rates: 235.8, p-value < 0.001 → significant differences between states.

* Some states consistently outperform others.

### *4. Predictive Modeling*
***Models Tested:***

* Random Forest Regressor

* Gradient Boosting Regressor

***Performance:***

| Model | MAE | RMSE | R^2 |
|:--------|:-----:|------:|------:|
| Random Forest |	2.03  | 3.84  | 0.893  |
| GradBoost   | 1.93  | 	3.45	|  0.913  |

\
***Feature Importance (GradBoost):***

* **MMR rate –** 89.98%

* **Personal exemptions (xper) –** 8.33%

* **Medical exemptions (xmed) –** 0.76%

* **Enrollment size –** 0.23%

* **Religious exemptions (xrel) –** 0.21%

* **State & school type –** < 0.2% each

> ***Key Finding:***
*MMR rate alone predicts overall vaccination rate with very high accuracy, while exemption rates provide additional explanatory power.*

### *5. Conclusion*
* *States and school types vary significantly in vaccination coverage.*

* *Private schools show lower coverage, which could be a public health concern.*

* *MMR rate is the strongest predictor of overall vaccination rates — tracking and improving MMR coverage could directly raise overall rates.*

* *The model can accurately predict missing overall rates, helping fill gaps in public health datasets.*

### *6. Next Steps*
* *Map vaccination rates by state and county to visually highlight hotspots.*

* *Study temporal trends to see if coverage is improving or declining.*

* Expand dataset with demographic and socio-economic indicators for richer analysis.*

***Citation:*** This data was completed by staff of The Wall Street Journal: Dylan Moriarty, Taylor Umlauf, & Brianna Abbot.


