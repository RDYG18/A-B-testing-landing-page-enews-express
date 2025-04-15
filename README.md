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

As part of the Data Science team, I analyzed interaction data from a randomized A/B test involving 100 participants, split evenly across control and treatment groups. The analysis was conducted at a 5% significance level to ensure statistical validity.

- **Business Questions Addressed for the Design Team:**  

- **Engagement Time Comparison:** Do users spend more time on the new landing page compared to the old one?

- **Conversion Rate Effectiveness:** Is the conversion rate significantly higher on the redesigned page?

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
