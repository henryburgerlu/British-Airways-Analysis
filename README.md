British Airways Data Science Project (Forage)

This repository contains two data science projects I completed as part of the **British Airways Virtual Experience Program**.
Forage Website: https://www.theforage.com/

These projects simulate real-world scenarios and offer hands-on experience with data analysis, machine learning, and deriving actionable business insights.
This project analyzed 50,000 customer booking records to understand what drives booking completion on the British Airways platform. The purpose of this project is to supports sales on focusing their apporach to come up with appealing
promotions and understand customer booking behaviors. 

## ✈️ Project 1: Web Scraping Customer Review Analysis

- **Overview**:  
  In this project, I scraped customer reviews and applied natural language processing (NLP) techniques to uncover key themes in feedback.
  
- **Key Techniques**:
  - Web scraping
  - Topic modeling (LDA)
  - Frequency analysis
  - Visualization using matplotlib and pandas

- **Goal**:  
  Identify recurring issues and positive highlights from customer reviews to support service improvement efforts.

**Business Recommendations**:
  Based on the findings,specific actions for enhancing customer experience—such as improving check-in processes and addressing frequent complaints about delays is provided.

---
### **Project 2: Holiday Booking Completion Analysis**

- **Overview**:
    
    This project focused on analyzing factors that influence whether a holiday booking is completed, using a structured dataset provided by Forage.
    
- **Key Techniques**:
    - Data cleaning and encoding
    - Random Forest classification
    - Hyperparameter tuning (GridSearchCV)
    - Model evaluation using AUC-ROC and accuracy
- **Goal**:
    
    Build a predictive model and uncover which customer and booking attributes most impact booking outcomes.
    

### **Summary**

#### **Using a Random Forest model evaluated with Stratified K-Fold Cross-Validation and a held-out test set, only about 15% of bookings are completed, so always predicting "not complete" already scores about 85% accuracy; accuracy is therefore not used to judge the model, and AUC-ROC, average precision and the precision/recall trade-off are used instead.**

**Model performance**

- Cross-validated AUC-ROC is about 0.78 (unweighted forest 0.781, sd 0.004) and average precision about 0.37, against a base rate of 0.15. On the held-out set the tuned model scores AUC-ROC 0.784 and average precision 0.375.
- This is a moderate ranking model, not a precise classifier. The top 10% of scored customers complete at about 42%, roughly 2.8x the base rate, and the top 20% of customers contain about half of all completed bookings.
- Class weighting did not improve the ranking: the balanced, depth-limited forest scored lower (AUC 0.764) than the unweighted forest, and a simple logistic regression reached 0.780.

**What drives the predictions** (drop in held-out AUC-ROC when a feature is shuffled)

- **booking_origin:** by far the largest (0.147)
- **route:** 0.056
- **length_of_stay:** 0.017
- **purchase_lead** (0.008), **flight_hour** (0.005) and **num_passengers** (about 0) add little.
- Booking origin and route carry related information, so their separate shares should not be over-interpreted.

**Direction of the effects** (completion rates in the data)

- By booking origin, completion ranges from 5.0% for Australia to 34.4% for Malaysia (Indonesia 26.0%, Thailand 23.2%).
- Shorter lead times convert slightly better (about 17% at 21 days or fewer versus 13–14% beyond 90 days).
- Shorter stays convert better (about 18–19% at 7 days or fewer versus about 10% at 14–60 days).
- The Mobile channel converts at 10.8% versus 15.5% on the internet channel.

# **Business Recommendation**

Since booking origin and route drive the model far more than customer behavior, British Airways should:

1. **Use the model to rank customers, then choose the cut-off by campaign capacity.**
    - Contacting the top-scored 10% reaches customers who complete at about 42%, with precision around 0.44.
    - Widening to 20% captures about half of all likely completed the booking (precision about 0.38), and about 30% captures about two thirds (precision about 0.33).
    - Reminders, loyalty offers or personalized messages can be targeted to the scored list instead of the whole customer base.
2. **Plan by market and route first.**
    - Malaysia, Indonesia and Thailand complete at 34%, 26% and 23%, so reminders there reach the most likely completed the process.
    - Australia is the largest segment (about 17,900 bookings) and completes at only 5%. That gap deserves its own investigation (pricing, payment options, booking flow) rather than being treated as a general behavior problem.
3. **Look into the Mobile channel.** Mobile bookings complete at 10.8% versus 15.5% on the internet channel. This has not been controlled for market mix, so check it within markets before changing the checkout experience.
4. **Treat lead time and trip length as secondary targeting hints.** Customers booking 21 days or less ahead, and trips of 7 days or less, convert modestly better. These effects are small compared with market, so they should refine targeting, not drive it.
5. **Do not assume add-ons cause completion.** Customers who want extra baggage or a preferred seat complete more often (16.7% versus 11.5%, and 17.7% versus 13.8%), but those choices are made inside the booking flow. Whether offering them earlier raises completion should be tested with an A/B experiment.

**Limitations and next steps:** the model ranks customers but is not a precise predictor (hold-out precision at a 20% cut-off is about 0.38), probabilities have not been calibrated, and the findings describe associations rather than causes. Next steps are to try smaller `min_samples_leaf` values, check calibration, and test the highest-value actions in a controlled experiment.

Purpose:  
This project was completed as part of my professional portfolio and learning journey. It provided hands-on practice with real business challenges and data.

Data Source:  
The dataset used in this project was provided by Forage as part of their publicly accessible virtual experience programs.

Credential  
I earned a certificate of completion for successfully completing this data science project via Forage.
This project was done independently through Forage’s open-access platform.

Disclaimer: I do not claim employment or official affiliation with British Airways.

