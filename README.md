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
## 🏖️ Project 2: Holiday Booking Completion Analysis

- **Overview**:  
  This project focused on analyzing factors that influence whether a holiday booking is completed, using a structured dataset provided by Forage.
  
- **Key Techniques**:
  - Data cleaning and encoding
  - Random Forest classification
  - Hyperparameter tuning (GridSearchCV)
  - Model evaluation using AUC-ROC and accuracy

- **Goal**:  
  Build a predictive model and uncover which customer and booking attributes most impact booking outcomes.
  
## Summary of Findings – British Airways Booking Completion Analysis
### Using a Random Forest model tuned through Stratified K-Fold Cross-Validation to handle imbalanced data, the top factors influencing whether a customer completes a booking were:

- **Purchase Lead**: (how early the booking is made) - most influential
- **Flight Hour**: (time of flight)
- **Length of Stay**: (duration of trip)
- **Number of Passengers**: (size of group)
- **Booking Origin**: (specific countries stood out)

Customers who booked further in advance, selected earlier flight hours, and had longer stays or more passengers were significantly more likely to complete their bookings.

Model AUC-ROC score (0.78) suggests the model can effectively prioritize leads and be used as a triage tool by the marketing team.
## Business Recommendation

Since purchase_lead is the strongest predictor, British Airways should:

Identify early planners (e.g., 40+ days in advance) and proactively engage them with:

Reminders to complete bookings

Loyalty incentives or personalized offers

Bundled upsells: Offer travel insurance, preferred seats, or meals at a discount to lock in commitment early

Travel insurance or extras like seats/meals to increase commitment

Additionally, flights with early departure hours and longer trip durations show higher conversion. These can be featured more prominently in marketing and search results.

The sales_channel_Mobile feature appears among the top predictors, suggesting platform choice may influence conversions, perhaps to look into streamlining UX and set up checkout reminders. 
Lastly, by combining behavioral insights with country-level booking patterns, targeted regional campaigns can be launched in high-performing markets (e.g., Malaysia showed significance in the model).

Purpose:  
This project was completed as part of my professional portfolio and learning journey. It provided hands-on practice with real business challenges and data.

Data Source:  
The dataset used in this project was provided by Forage as part of their publicly accessible virtual experience programs.

Credential  
I earned a certificate of completion for successfully completing this data science project via Forage.
This project was done independently through Forage’s open-access platform.

Disclaimer: I do not claim employment or official affiliation with British Airways.

