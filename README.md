# U.S. Healthcare Data Breach Analysis (2010-2025)

## Project Overview
Healthcare data breaches have become one of the most consequential cybersecurity challenges facing the United States. As patient records, billing systems, and clinical infrastructure become increasingly digitzed and interconnected, the healthcare sector has emerged as a prime target for sophisticated cyberattacks, with breaches affecting millions of individuals and exposing deep vulnerabilities in how sensitive data is protected. 

This project analyzes healthcare-related data breaches reported to the U.S. Department of Health and Human Services (HHS) between the years 2010 and 2025 (with partial-year 2009 and 2026 data included in the full dataset, but excluded from trend analyses). Using Python for statistical analysis and machine learning, and Tableau for interactive visualization, it explores trends in breach frequency, severity, geographic distribution, and entity vulnerability, and predictability, with the goal of identifiying systemic patterns in how and where breaches are occurring across the U.S. healthcare sector. 

## Key Findings
This analysis of U.S. Healthcare data breaches from 2010 to 2025 uncovers several critical trends shaping the cybersecurity landscape in the healthcare sector. These insights paint a vivid picture of an evolving threat landscape where breach frequency and impact are increasingly driven by sophisticated, infrastructure-targeted attacks.  

- ### Massive Surge in Breaches:
Reported breaches grew from 199 in 2010 to a peak of 743 in 2023, a 273% increase, before declining sharply in 2024 and 2025. 

- ### Shift from Physical to Cyber Breaches:
Hacking/IT Incidents became the dominant and fastest-growing breach type over the 16-year period, while Theft, Loss, and Improper Disposal declined to a low, stable baseline. 

- ### Disproportionate Impact:
Just ten breaches account for 26.5% of all individuals affected across the entire period, with Change Healthcare alone impacting an estimated 190 million people.

- ### Geographic Disparities:
California, Texas, and New York report the highest breach counts, while Indiana's moderate breach volume masks a catastrophic impact, driven by the 2024 Change Healthcare breach.

- ### Severity is Hard to Predict:
A Random Forest classifier achieved 53% accuracy predicting breach severity from administrative metadata, suggesting that breach severity depends more on organization-specific circumstances than on entity type or breach mechanism alone.

- ### Systemic Infrastructure Risk:
All ten of the most harmful breaches targeted Network Servers, underscoring a critical and recurring vulnerability in healthcare IT infrastructure. 


## Tableau Dashboard 

[Explore the Interactive Dashboard on Tableau Public!](https://public.tableau.com/app/profile/lindsay.whipple/viz/U_S_HealthcareDataBreachTrends2010-2025/U_S_HealthcareDataBreachTrends2010-2025)


## Python Analysis

### 1. Entity Type Breakdown by Year

#### Entity Type Breakdown by Year Python 

![BreachCountbyYear](images/BreachCountbyYear.png)

#### Entity Type Breakdown by Year Tableau

![BreachesbyType](images/BreachesbyType.png)

#### Entity Type Breakdown by Year Analysis
An examination of breach distribution across entity types from 2010 to 2025 revealed that Healthcare Providers have consistently accounted for the majority of reported breaches throughout the entire period, ranging frm a low of 63.3% in 2014 to a high of 79.6% in 2017. Business Associates show the most fluctuation of any entity type, peaking at 23.8% in 2014 and 23.3% in 2023 before declining to 15.1% in 2025. Health Plans and Healthcare Clearinghouses remain consistently low across all years. 

A chi-square test of independence revealed a statistically significant change in entity type distribution over time (χ² = 231.67, df = 45, p <0.001), indicating that while Healthcare Providers remain dominant, the proportional involvement of different entity types has meaningfully shifted across the 16-year period. Notably, the rise and subsequent decline of Business Associate breaches in the early-to-mid 2010s and again in the early 2020s may reflect evolving regulatory scrutiny following the 2013 Omnibus Rule, which expanded direct liability for Business Associates. 


### 2. Breach Count by Year

#### Total Affected per Year Python

![TotalAffectedperYear](images/TotalAffectedperYear.png)

#### Total Affected per Year Tableau

![TotalAffected](images/TotalAffected.png)

#### Total Affected per Year Analysis

Between 2010 and 2025, reported healthcare data breaches increased dramatically, rising from 199 in 2010 to a peak of 743 in 2023-- a 274% increase over the period. Growth was largely steady throughout the 2010s, with notable acceleration beginning in 2019 (38.5% increase over 2018) continuing through the early 2020s. Breach counts plateaued between 2021 and 2023, each year hovering around 715-743 incidents, before declining sharply in 2024 (-14.8%) and again in 2025 (-47.7%).

A chi-square test of independence confirmed a statistically significant association between breach type and year (χ² = 4463.02, p < 0.0001), indicating that not only has breach volume changed over time, but the composition of breach types has shifted meaningfully as well. 

It is worth noting that the sharp decline in 2024 and 2025 does not necessarily indicate an improvement in healthcare cybersecurity-- reporting lags and the time between breach occurrence and HHS submission may mean recent years are undercounted relative to their true totals. 


### 3. Breach Type Evolution

#### Breach Type Evolution Python

![MapBreachesvsAffected](images/MapBreachesvsAffected.png)


#### Breach Type Evolution Tableau

![Map](images/Map.png)

#### Breach Type Evolution Analysis 

Pairwise proportion z-tests were conducted for each of the five main breach categories, Hacking/IT Incidents, Unauthorized Access/Disclosure, Theft, Loss, and Improper Disposal, comparing each consecutive year pair as well as each year against 2025. 

Hacking/IT Incidents show the most dramatic and consistent upward trend of any breach type, with nearly every year compared against 2025 highly significant (p < 0.0001). Theft, Loss, and Improper Disposal all show a clear and consistent decline over the period, reflecting that physical breach mechanisms have been largely replaced by cyber-based ones. Taken together, these results paint a clear picture of a sector-wide shift from physical to cyber-based breach mechanisms over the past 15 years. 

### 4. Geographic Analysis: Breaches vs. Affected

#### Geographic Analysis Python

![TypeBreakdown](images/TypeBreakdown.png)

#### Geographic Analysis Tableau

![BreachedEntityType](images/BreachedEntityType.png)

#### Geographic Analysis 

California, Texas, and New York report the highest raw breach counts at 698, 564, and 456 respectively, likely reflecting their large populations and concentrations of healthcare infrastructure. A Pearson correlation of 0.73 between breach count and total individuals affected indicates a moderate positive relationship, but Indiana stands out as a striking exception -- 185 reported breaches but over 92 million individuals affected (Z-score of 4.56), almost certainly driven by the 2024 Change Healthcare breach. These findings underscore that breach frequency and breach severity are distinct dimensions of risk. 

### 5. Top 10 Harmful Breaches

#### Top 10 Harmful Breaches Python

![Top10Harmful](images/Top10Harmful.png)

#### Top 10 Harmful Breaches Tableau

![Top10](images/Top10.png)

#### Top 10 Harmful Breaches Analysis 

The ten most harmful healthcare data breaches collectively affected over 178 million indivudals, accounting for 26.5% of all indivduals affected across the entire period. A Mann-Whitney U test confirms this disparity is statistically significant (U = 69,500, p < 0.0001). Nine of the ten most harmful breaches were Hacking/IT Incidents, and all ten targeted Network Servers. Despite Healthcare Providers accounting for the majority of breaches overall, Business Associates and Health Plans dominate the top 10, suggesting the most catastrophic breaches tend to occur at the vendor and insurance level. 

### 6. Machine Learning: Severity Classification 

#### Severity Classification Python



#### Severity Classifcation Tableau



#### Severity Classification Analysis

A Random Forest classifier was trained to categorize breaches into Low, Medium, and High severity tiers based on entity type, breach type, location, state, year, business associate involvement, and engineered geographic features. The model achieved 53% accuracy, with feature importance distributed relatively evenly across engineered geographic features rather than dominated by any single predictor, suggesting breach severity is driven less by the category of organization or attack type and more by the specific circumstances of where a breach occurs. 

### 7. Machine Learning: Anomaly Detection

#### Anomaly Detection Python



#### Anomaly Detection Tableau



#### Anomaly Detection Analysis

An Isolation Forest model flagges the most unusual 2% of breaches (n = 136) across multiple dimensions simultaneously. Anomalies split into two distinct groups: the largest, most catastrophic breaches (Anthem, Kaiser, HCA Healthcare), and breaches near the minimum reportable threshold occurring in states where the typical breach is far more severe, demonstrating the value of multivariate anomaly detection over simple univariate outlier methods. 

### 8. Machine Learning: Time Series Forecasting

### Forecasting Python



#### Forecasting Tableau



#### Forecasting Analysis

Linear and polynomial regression models were fit to yearly breach counts to project future volume. The linear model (R² = 0.623) projects continued growth, while the polynomial model (R² = 0.657) projects a leveling off- better capturing the recent plateau-and-decline pattern in the data. Neither achieves a particularly strong fit, itself a meaningful finding given the structural shifts in the underlying trend.

### 9. Machine Learning: State Clustering

#### State Clustering Python



#### State Clustering Tableau



#### State Clustering Analysis

K-Means clustering (k=4) on state-level breach count, total affected, and average severity revealed four interpretable risk profiles: Indiana as a singleton extreme-outlier, a high-volume cluster (CA, FL, NY, TX), a moderate-risk tier of 20 states with elevated average severity, and a lower-risk cluster of 27 states. 

## Conclusion

This analysis of U.S. healthcare data breaches from 2010 to 2025 reveals a sector under growing and increasingly sophisticated cyber threat. Breach volume surged dramatically over this period, and while 2024 and 2025 saw declines, this may reflect reporting lag as much as genuine improvement. Hacking and unauthorized access have emerged as the dominant breach mechanisms, with network servers targetd in every one of the ten most harmful breaches. 

The machine learning analysis adds an important layer of nuance: breach severity proved difficult to predict from administrative metadata alone, suggesting that meaningful risk forecasting would require richer data- such as organization-specific security posture or the type of data exposed. Geographic clustering further reveals that breach risk is not one-dimensional, but spans distinct profiles of volume-driven and severity-driven risk. 

Taken together, these findings point to an urgent need for modernized server security practices, stronger infrastructure safeguards, and greater investment in breach prevention- particularly among large healthcare providers, business associates, and the organizations most exposed to catastrophic, infrastructure-level attacks. 
