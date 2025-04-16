# Enews Express testing landing page

<p align="center">
  <img src="https://github.com/user-attachments/assets/eed18cf8-adae-4436-b3f5-b21d7f7120db" width="500"/>
</p>


## Company Context

<div align="justify">
  
As a Data Scientist at E-news Express, a digital media company focused on delivering timely and personalized news content, I was tasked with analyzing user engagement to support subscriber growth. The company operates in a highly competitive online news market, where attracting and retaining readers has become increasingly challenging.In recent months, the desing team raised concerns about a steady decline in new monthly subscriptions. Preliminary data suggested that the current landing page design was not effectively capturing user interest. In response, the design team proposed a new version with revised layout and content.

To evaluate the impact of these changes, we launched an A/B testing initiative. The goal was to measure differences in key metrics such as user engagement and conversion rates so the desing team could make informed decisions about whether to proceed with a full migration to the new design.


</div>

---

## Objective 

<div align="justify">
  
The objective of this project was to evaluate whether a newly designed landing page led to higher user engagement and conversion rates compared to the existing version. The desing team at E-news Express requested this analysis to inform future decisions around content layout and user experience optimization.

As part of the Data Science team, I analyzed interaction data from a randomized A/B test involving 100 participants, split evenly across control and treatment groups. The analysis was conducted at a 5% significance level to ensure statistical validity and to address the key questions posed by the design team.

- **Business Questions Addressed for the Design Team:** ¿Did the new landing page lead to a statistically significant increase in user engagement, as measured by session duration?

- **Engagement Time Comparison:** ¿The new landing page lead to a statistically significant increase in user engagement, as measured by session duration?

- **Conversion Rate Effectiveness:** ¿Did the new landing page lead to a statistically significant increase in conversion rate compared to the original version, as measured by the proportion of users who subscribed after visiting each page?

- **Language-Based Conversion Differences:** Does language preference affect conversion rates?

- **Consistency of Engagement Across Languages:** Is time-on-page consistent across different language groups?


</div>

---
## Dataset

### Data Structure

The dataset captures user interaction with two different versions of a landing page as part of an A/B test conducted by E-news Express. Each row represents a unique website visit by a single user.

The dataset contains **100 rows** and **6 columns**, with no null values or duplicates, and has the following structure:

**user_id (int64):** A unique identifier for each user in the experiment.

**group (object):** Indicates whether the user was assigned to the control group (original landing page) or treatment group (redesigned landing page).

**landing_page (object):** Specifies which version of the landing page the user was shownmeither 'old_page' or 'new_page'.

**time_spent_on_the_page (float64):** The amount of time (in minutes) the user spent on the landing page during their session.

**converted (object):** Indicates whether the user subscribed to the platform after viewing the page. Values are typically 'yes' or 'no'.

**language_preferred (object):** The language selected by the user to view the page 'English', 'Spanish', 'French'.

---

## Exploratory Data Analysis (EDA)

### Univariate Analysis 


**Time Spent on the Page**

<div align="justify">

The distribution of time spent on the page shows that the median duration is approximately 5.4 minutes, meaning that half of the users interacted with the page for less time and half for more. The interquartile range (IQR) spans from 3.8 minutes (Q1) to 7.0 minutes (Q3), indicating that the middle 50% of users had relatively consistent engagement. There are no extreme outliers in the data, and the overall time spent ranges from 0.6 to 10.5 minutes fall within a reasonable spread, indicating that all users spent at least a few seconds on the page.

</div>
 

<div align="center">
  <img src="https://github.com/user-attachments/assets/f9c91f72-c8a8-496d-b563-8b043fbbc2b4" width="500"/>
</div>



**Conversion Status**

Among the 100 participants in the A/B test, 54% converted, while 46% did not. This near-even split indicates a relatively well-balanced outcome, making it a suitable dependent variable for statistical comparison between groups.

<div align="center">
  <img src="https://github.com/user-attachments/assets/e5de0a52-8e2b-4e96-8b5f-a3d873397c77" width="500"/>
</div>

**Language Preference**

The distribution of users by their preferred language when viewing the landing page. Among the 100 participants, Spanish and French were each selected by 34 users, while English was chosen by 32 users. The nearly even distribution across all three languages suggests a well-balanced audience.

<div align="center">
  <img src="https://github.com/user-attachments/assets/6d8d24cf-1451-4c92-95da-99f0cc4a8f88" width="500"/>
</div>


### Bivariate Analysis

**Conversion Status vs Time Spent on the Page**

This shows the distribution of time spent on the landing page between users who converted (yes) and those who did not (no).

- Users who converted spent more time on average, with a median of approximately 6.6 minutes, compared to 4.0 minutes for those who did not convert.

- The interquartile range for converted users (5.4 to 7.7 minutes) is both higher and narrower than that of non-converted users (2.3 to 5.2 minutes), indicating more consistent and sustained engagement among those who subscribed.

- There are more high value outliers in the converted group, suggesting that longer visits were not uncommon among those who eventually subscribed.

- The presence of low time outliers in the non-converted group also points to users who bounced quickly.

<div align="center">
  <img src="https://github.com/user-attachments/assets/87d5daf4-4f5a-497e-9eab-d53ff53462d6" width="500"/>
</div> 

**Interpretation:**

There is a clear difference in engagement behavior between converters and non-converters. The findings suggest that spending more time on the landing page is associated with a higher likelihood of subscription, reinforcing the idea that content depth, layout clarity, or overall page experience could be influencing conversion decisions. This supports the need to optimize for elements that retain user attention longer.

**Landing Page Version vs Time Spent**

We can see the comparison of the time users spent on the original landing page versus the redesigned version.

- Users who visited the new landing page spent more time on average, with a median of approximately 6.2 minutes, compared to 4.4 minutes for those who saw the old version.

- The interquartile range (IQR) for the new page is also narrower and shifted upwards, suggesting more consistent engagement at a higher level.

- Both versions show some outliers. The new page has higher-value outliers, indicating that some users may have liked the page and stayed longer in order to explore all its aspects. Conversely, lower-value outliers suggest that some users left quickly, possibly due to a lack of interest or poor initial impression.

- The lower whisker of the old page dips below 1 minute, while the new page maintains a higher minimum engagement time. This suggests that users may have found the new landing page more engaging or enjoyable to interact with..

  
<div align="center">
  <img src="https://github.com/user-attachments/assets/f6ff20bf-7a43-4dfe-95de-3491559320f8" width="500"/>
</div> 

**Interpretation:**

<div align="justify">
  
The new landing page appears to be more effective at retaining user attention. The increase in median time spent, along with more concentrated and elevated engagement levels, suggests improvements in content layout or user experience. This supports the hypothesis that the redesign positively impacted how users interact with the page and provides preliminary evidence in favor of adopting the new version.

</div>

**Language Preference vs Time Spent**

This boxplot compares the time spent on the landing page across the three language groups: Spanish, English, and French.

- Users who selected Spanish as their preferred language show a slightly higher median (5.7 minutes) with a relatively compact interquartile range, indicating consistent engagement.

- English speaking users display the widest IQR, ranging from under 3 minutes to over 7, and also include both very short and very long session outliers, reflecting more diverse usage patterns.

- French speaking users show a median around 5.2 minutes, with a slightly right skewed distribution, including some high-value outliers above 10 minutes.

<div align="center">
  <img src="https://github.com/user-attachments/assets/9c8cce71-f38b-413f-b2e3-b596aae005c7" width="500"/>
</div> 

Interpretation:

<div align="justify">
  
Although all three groups show comparable medians (between 5.2 and 5.7 minutes), the variance in engagement differs notably by language. Spanish-speaking users tend to have more uniform time on page, while English and French users exhibit a broader range of interaction. This variation may indicate that the landing page content is better tailored or more intuitive for Spanish-speaking users, whereas users in the other language groups may encounter sections that are less engaging, harder to navigate, or not fully localized.

</div>

---
##  A/B Testing – Time Spent on Page

<div align="center">
  <img src="https://github.com/user-attachments/assets/3db06f5b-d137-459e-ae3e-3b9f263baf0b" width="600"/>
</div> 

####  ¿Did the new landing page lead to a statistically significant increase in user engagement, as measured by session duration?

To assess whether the **redesigned landing page increased user engagement**, we performed an independent samples t-test using the `ttest_ind` function from the `scipy.stats` library. The analysis compared the **mean time spent on the page** between users exposed to the **new version** and those shown the **original version**.

The test was conducted under the assumption of **equal variances** between groups. A **one-tailed hypothesis** was defined with the following setup:

- **Null Hypothesis (H₀):** The mean time spent on the new page is less than or equal to that on the old page.  
- **Alternative Hypothesis (H₁):** The mean time spent on the new page is greater than that on the old page.

A significance level of **α = 0.05** was used to evaluate the result. The t-test returned a **p-value of 0.0048**, which is below the defined threshold.

**Interpretation:**  
There is sufficient statistical evidence to reject the null hypothesis and accept the alternative. This suggests that users spend significantly more time on the new landing page compared to the existing version. The result aligns with and reinforces the pattern observed in the exploratory boxplot analysis, where higher session durations were visually concentrated among users exposed to the new design. Together, the statistical outcome and visual evidence support the conclusion that the redesign had a positive impact on user engagement, providing a strong basis for the design team to proceed with a full rollout.


## A/B Testing – Conversion Rate 

<div align="center">
  <img src="https://github.com/user-attachments/assets/3047cb56-79f7-4032-aad8-12c3b8b60f94" width="500"/>
</div> 

#### ¿Did the new landing page lead to a statistically significant increase in conversion rate compared to the original version, as measured by the proportion of users who subscribed after visiting each page?

To evaluate whether the **redesigned landing page led to a higher conversion rate**, we performed a **two-sample z-test for proportions** using the `proportions_ztest` function from the `statsmodels.stats.proportion` module. The test compared the **conversion rate** between users exposed to the **new landing page** (treatment group) and those shown the **original version** (control group).

The groups were independent, and each user's conversion outcome was binary (`yes` or `no`). A **one-tailed test** was performed under the following hypotheses:

- **Null Hypothesis (H₀):** The conversion rate for the new page is less than or equal to the conversion rate for the old page.  
- **Alternative Hypothesis (H₁):** The conversion rate for the new page is greater than the conversion rate for the old page.

The test was conducted at a **significance level of α = 0.05**. The z-test returned a **p-value of 0.0080**, which is below the defined threshold.

**Interpretation:**  
There is sufficient statistical evidence to reject the null hypothesis and conclude that the conversion rate on the new landing page is significantly higher than that of the old version. This suggests that the design changes not only improved engagement, but also led to a measurable increase in the proportion of users subscribing. These findings support the business decision to move forward with the new landing page.Is also visually supported by the stacked proportion bar chart, where a noticeably larger share of users converted on the new landing page compared to the old one. The clear difference in the visual distribution of conversion outcomes reinforces the statistical result and strengthens the case for adopting the new design.

## A/B Testing – Conversion vs Language Preference

<div align="center">
  <img src="https://github.com/user-attachments/assets/5c513e33-fc4e-4061-9c20-6dfe76afe6d7"width="500"/>
</div> 

### Is there a statistically significant relationship between a user’s preferred language and their likelihood of conversion on the landing page?

To evaluate whether a user’s **preferred language is associated with conversion behavior**, we conducted a **Chi-square test of independence** using the `chi2_contingency` function from the `scipy.stats` module. The test examines the relationship between two categorical variables: **`converted` status** (`yes` or `no`) and **`language_preferred`** (`English`, `French`, `Spanish`).

A contingency table was created based on the observed frequencies of conversions across the three language groups.

The test was performed using the following hypotheses:

- **Null Hypothesis (H₀):** Conversion status and preferred language are independent.  
- **Alternative Hypothesis (H₁):** Conversion status and preferred language are dependent.

A significance level of **α = 0.05** was used to assess statistical evidence. The resulting **p-value was 0.2130**, which is above the significance threshold.

**Interpretation:**
The test did not return statistical evidence of a significant relationship between conversion status and preferred language. This result aligns with what was observed during the exploratory data analysis, where the **stacked proportion bar chart** of conversions by language showed relatively balanced distributions across the three language groups. While minor differences exist—such as a slightly higher conversion proportion among English speakers—the visual patterns do not suggest meaningful disparities. The **Chi-square** result supports the idea that these variations are likely due to chance rather than a true association between language preference and conversion behavior.

## A/B Testing – Session Duration on New Page by Language

<div align="center">
  <img src="https://github.com/user-attachments/assets/8305f209-e033-4539-818a-9855678a510b" width="500"/>
</div> 

### ¿Is there a statistically significant difference in session duration on the new landing page across users with different language preferences?

To determine whether **session duration on the new landing page varies depending on the user's preferred language**, we conducted a **one-way ANOVA test** using the `f_oneway` function from the `scipy.stats` module. This test compares the **mean time spent on the page** across three independent groups: **English**, **French**, and **Spanish** speakers.

The test was structured under the following hypotheses:

- **Null Hypothesis (H₀):** The mean time spent on the new page is the same for all language groups.  
- **Alternative Hypothesis (H₁):** The mean time spent on the new page differs for at least one language group.

The analysis was conducted using a **significance level of α = 0.05**. The test returned a **p-value of 0.432**, which is well above the threshold.

**Interpretation:**  
The test does **not provide statistical evidence** of a meaningful difference in session duration across language groups on the new landing page. This finding is visually supported by the boxplot, where the medians and distributions of session times for English, French, and Spanish users appear relatively similar, with no group showing a distinctly higher or lower pattern. While minor fluctuations exist, the overall variance is not statistically significant, suggesting that **user engagement with the new design is consistent across languages**.
