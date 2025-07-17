# Vet Clinic Success: A Data-Driven Strategy for New Investors

## Brief Project Description

This project analyzes the New York City Dog Licensing dataset to provide actionable, data-driven insights for investors looking to open a new veterinary clinic. By examining dog demographics, population trends, and geographic distribution, we have developed a clear, low-risk strategy focused on a reliable and concentrated target market.

## Our Stakeholder

**Stakeholder:** New Veterinary Clinic Investors

Our stakeholder is an individual or group of investors aiming to establish a new, successful veterinary practice in New York City. They are seeking a data-backed strategy to minimize risk and focus their financial and marketing efforts for the highest probability of success.

## Core Business Problem

The central question this project addresses is: **"How can a new vet clinic focus its efforts to create a successful practice in a competitive market like New York City?"**. Our goal is to replace guesswork with a clear, factual strategy to guide key business decisions, from service offerings to marketing campaigns.

-----

## Exploratory Data Analysis (EDA)

Our analysis began with the raw NYC Dog Licensing dataset. The initial data required significant cleaning and preparation to become useful for generating business insights.

### Data Cleaning Process

The raw data was processed using a Python Jupyter Notebook with the `pandas` library. Key cleaning steps included:

1.  **Loading Data:** The `Dog_licensing.csv` dataset was loaded into a pandas DataFrame.
2.  **Handling Missing Values:** Rows with any null values were dropped to ensure data integrity (`.dropna()`).
3.  **Calculating Dog Age:** A new `Age` column was engineered by subtracting the `AnimalBirthYear` from the `Extract Year`.
4.  **Cleaning Age Data:** The `AnimalBirthYear` and `Extract Year` columns were converted to numeric types. Any rows where this conversion failed were dropped. We then filtered the `Age` column to include only realistic values (between 0 and 30 years) to remove outliers and invalid data points.

*Code Snippet for Age Calculation and Cleaning:*

```python
df[['Extract Year', 'AnimalBirthYear']] = df[['Extract Year', 'AnimalBirthYear']].apply(pd.to_numeric, errors='coerce')
df = df.dropna(subset=['Extract Year', 'AnimalBirthYear'])
df['Age'] = df['Extract Year'] - df['AnimalBirthYear']
df = df[df['Age'].between(0, 30)]
```

The cleaned dataset, `Dog_licensing_cleaned.csv`, was then exported for visualization and further analysis.

### Data Visualization and Key Findings

Our analysis revealed three certainties that form the foundation of our strategic recommendation.

**1. The Market is Overwhelmingly Young**

While the average age of a licensed dog in NYC is 6.0 years, the age distribution histogram clearly shows a massive peak for dogs between 1 and 4 years old. This demographic represents a "fountain of youth" for a new clinic—a constant and significant stream of new patients requiring foundational care like vaccinations, spay/neuter procedures, and initial wellness checks.
<img width="567" height="464" alt="Screenshot 2025-07-16 at 3 06 12 PM" src="https://github.com/user-attachments/assets/03fe5344-6530-42d9-b633-bde9892054e3" />
<img width="564" height="215" alt="Screenshot 2025-07-16 at 3 10 18 PM" src="https://github.com/user-attachments/assets/c11356a5-e9d9-4287-83cd-b67962e95be9" />

**2. The Youthful Trend is Stable and Reliable**

To ensure this youth boom isn't an anomaly, we analyzed the average dog age by the year the data was extracted. The trend shows that the average age has remained consistently young and stable over time. Although there is a data gap from 2019-2021 (likely due to the COVID-19 pandemic's impact on data collection), the consistency before and after this period gives us confidence that this core demographic is reliable and allows for confident, long-term business planning.
<img width="1141" height="270" alt="Screenshot 2025-07-16 at 3 08 02 PM" src="https://github.com/user-attachments/assets/b6d79c5d-ca0b-4d3b-8162-6d76882003bb" />

**3. The Target Market is Geographically Concentrated**

The analysis of dog populations by zip code provides a "treasure map" for targeted marketing. We found that the licensed dog population is highly concentrated in specific neighborhoods, particularly within Manhattan and Brooklyn. This allows for incredibly efficient marketing spend, focusing efforts and resources only on these high-density areas.

<img width="581" height="540" alt="Screenshot 2025-07-16 at 3 09 09 PM" src="https://github.com/user-attachments/assets/d8061bda-4b6b-4ff7-87e8-58b333a4a166" />
<img width="572" height="256" alt="Screenshot 2025-07-16 at 3 09 44 PM" src="https://github.com/user-attachments/assets/cbccc7a0-3e58-4d68-99c6-22cd88a09622" />

### Tableau Dashboard

For a more interactive exploration of these insights, please view our Tableau dashboard.

[**Link to Tableau Dashboard**](https://public.tableau.com/app/profile/angel.bautista/viz/Mod2ProjectDogDashboard/VetClinicDashboard)

-----

## Business Recommendations

Our analysis of the data points to a clear, three-pronged strategy for a successful new vet clinic.

The Three Certainties are:

  * The market is **Young**.
  * This trend is **Reliable**.
  * The population is **Concentrated**.

Based on these facts, we recommend the following strategic actions:

1.  **Focus on Foundational & Preventative Care:** Build your clinic's services around the 1-4 year old demographic. This means prioritizing puppy/kitten vaccination packages, spaying and neutering services, and preventative wellness plans. This focus directly serves the largest and most reliable segment of the market.

2.  **Invest with Confidence for the Long Term:** The stability of the market's age demographic demonstrates that the demand for youth-focused veterinary services is not a fleeting trend. This allows for confident long-term investment in facilities, equipment, and staff training centered on primary and preventative care.

3.  **Execute a Hyper-Targeted Marketing Strategy:** Use the geographic insights as a guide for all marketing efforts. Concentrate your budget on the top 10 zip codes with the highest dog populations. This precision targeting will maximize your return on investment by reaching the highest density of potential customers and avoiding wasteful spending in lower-density areas.

-----

## Project Reflection

  * **What’s the most important insight your dashboard reveals?**
    The most crucial insight is the combination of the three certainties: the market is not just young, but it is **stably and reliably young** and **geographically concentrated**. A single insight, like the youth peak, is valuable. However, knowing this trend is consistent over time and that we know exactly where these customers live transforms a simple observation into a powerful, low-risk business strategy.

  * **With limited time, how did you decide what features or visuals to prioritize in your dashboard?**
    Our priority was to directly and clearly answer the core business question for our stakeholders and nothing else. We have cleaned our data to only answer our business question as the project length was very short. Every visual was chosen to support one of the three core pillars of our recommendation: Who are the customers? (Age Distribution), Is the market stable? (Age Over Time), and Where are they? (Dogs by Zip Code). We avoided more complex or peripheral analyses to maintain a sharp focus on providing actionable, strategic insights that an investor could immediately use to build a business plan.

## Repo Navigation

  * **/data**: Contains the raw (`Dog_licensing.csv`) and cleaned (`final_dataset.csv`) data files.
  * **cleaning_and_eda.ipynb**: The Jupyter Notebook used for all data cleaning, processing, and visualization.
  * **README.md**: This file, providing a complete overview of the project.

## Group Members & Linkedin

  * **Angel Bautista**: https://www.linkedin.com/in/angel-bautista-ba2228367/
  * **Kabbo Sultan**: https://www.linkedin.com/in/kabbosultan/
