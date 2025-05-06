
# Bellabeat Smart Device Data Analysis for Product Strategy

## About the company

Bellabeat is a high-tech company that manufactures health-focused smart products. They offer different smart devices that collect data on activity, sleep, stress, and reproductive health to empower women with knowledge about their own health and habits.

## Stakeholders

* Urška Sršen: Bellabeat’s cofounder and Chief Creative Officer
* Sando Mur: Mathematician and Bellabeat’s cofounder; key member of the Bellabeat executive team
* Bellabeat product analytics team: A team of data analysts responsible for collecting, analyzing, and reporting data that helps guide Bellabeat’s product strategy.

## Business task

Urška Sršen, cofounder and Chief Creative Officer of Bellabeat, believes that analyzing smart device fitness data could help unlock new growth opportunities for the company. You have been asked to focus on one of Bellabeat’s products and analyze smart device data to gain insight into how consumers are using their smart devices. The insights you discover will help guide the company's product strategy, enabling the team to prioritize features that enhance user engagement, promote healthier habits, and align with user behavior patterns.


![Logo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQKHzAfpIe2A7xzX7CH7sBY2iuQaAW2hRLgBQEuKIx_06m3jYamvRYcTmIXHYFRLbYZwxg&usqp=CAU)


## Data - Source and Integrity

Dataset is from https://www.kaggle.com/datasets/arashnic/fitbit which is an open-source dataset with usability rating of 10.00.

The dataset is:

* **Reliable**: The data is from 30 eligible FitBit users who consented to the submission of personal tracker data to a distributed survey via Amazon Mechanical Turk.
* **Original**: The data is from 30 eligible FitBit users who consented to the submission of personal tracker data to a distributed survey via Amazon Mechanical Turk.
* **Comprehensive**: The personal tracker data includes minute-level output for physical activity, heart rate, and sleep monitoring.
* **Cited**: Furberg, Robert; Brinton, Julia; Keating, Michael ; Ortiz, Alexa https://zenodo.org/record/53894#.YMoUpnVKiP9

We have been provided with 18 CSV documents with each document representing the different quantitative data tracked by the smart device. The data is in long format since each row is one time point per subject (activity’s date and time), so each subject (user with unique ID) will have data in multiple rows.

The **limitations of the dataset** include:

Extremely small sample size.
The data is outdated as it was collected from March 2016 to May 2016.
Details like the age, geographical location of the Fitbit user is not available. Moreover, Bellabeat is a women's fitness-based company, hence there is no proper representation across genders.
These conditions could lead to sampling bias.


## Executive Summary

### Overview of Findings

**1. Calories vs steps**

<img src="https://www.kaggleusercontent.com/kf/235179192/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..XyhqfU0QeReDEoNmzQoH8Q.c5HDUUpuBf6YxuKMdEMsEIXishkq17c-0erJWrG-3FWiHTtnamu4tXK9QbYHFQ0uDLYybiQeX4zRmKXJIOt29w3KXn5rKonwKq5Qq72WaMC8MwN1SMWNwc4XBqzT_u6rIB8rEthRNl9GVVoyVGbJIbks43eZ9YrApGhmOK4teVovE_ueakzpy79IIvMt19_HKILNBbDOITlZye4MTHE0SgMjUNm6KPDafVIUNxm6PWtcLCTM7p8alxklgQxpnjDxPBoLuUAi_SfnGh6Dw_0kyar-xuGt0KsJ9a6Ri68BroT21vofY8ISA8gCd9D4dnNY-c4BqNKzERUhyvmOh4tT-VAZH-2_q7a0Y9DjTzm0aYHyrQSPL-9iV8SfyiI8kMmptyYYLnJ67Ojdxz66hJ5X8MYkDdV0CgCfN6zaXAt_MF2WcDkzemZHnvIrsSr5vYhfxmVmlU5Q1giRBtk3wNtmrUThfPP3t9utZyXqvuZCJgdEkd69E_WquD2Q7VRFISRHz1JZLQuuCrk0rkGmtwe4GHQ_HRkbOhSFcYey441XrbYywluMc-L_ZJnI0nKhxcxt1It7HqtkeUMkuiItyr13nzTE37yJAy5pNKg8YgHG-Y6k4v8juSzwN3XrYYOx8PPSXf9QBIjXKbvX-q74OxS6nA.78spGWXnLcDGxAT2kV230A/__results___files/__results___32_1.png" alt="Viz Image" width="400" height="450">

There is a positive correlation between steps and calories burned. The more steps walked, the more calories can be burned.

**2. Total steps vs minutes asleep**

<img src="https://www.kaggleusercontent.com/kf/235179192/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..XyhqfU0QeReDEoNmzQoH8Q.c5HDUUpuBf6YxuKMdEMsEIXishkq17c-0erJWrG-3FWiHTtnamu4tXK9QbYHFQ0uDLYybiQeX4zRmKXJIOt29w3KXn5rKonwKq5Qq72WaMC8MwN1SMWNwc4XBqzT_u6rIB8rEthRNl9GVVoyVGbJIbks43eZ9YrApGhmOK4teVovE_ueakzpy79IIvMt19_HKILNBbDOITlZye4MTHE0SgMjUNm6KPDafVIUNxm6PWtcLCTM7p8alxklgQxpnjDxPBoLuUAi_SfnGh6Dw_0kyar-xuGt0KsJ9a6Ri68BroT21vofY8ISA8gCd9D4dnNY-c4BqNKzERUhyvmOh4tT-VAZH-2_q7a0Y9DjTzm0aYHyrQSPL-9iV8SfyiI8kMmptyYYLnJ67Ojdxz66hJ5X8MYkDdV0CgCfN6zaXAt_MF2WcDkzemZHnvIrsSr5vYhfxmVmlU5Q1giRBtk3wNtmrUThfPP3t9utZyXqvuZCJgdEkd69E_WquD2Q7VRFISRHz1JZLQuuCrk0rkGmtwe4GHQ_HRkbOhSFcYey441XrbYywluMc-L_ZJnI0nKhxcxt1It7HqtkeUMkuiItyr13nzTE37yJAy5pNKg8YgHG-Y6k4v8juSzwN3XrYYOx8PPSXf9QBIjXKbvX-q74OxS6nA.78spGWXnLcDGxAT2kV230A/__results___files/__results___34_1.png" alt="Viz Image" width="400" height="450">

There is no correlation between the total number of steps walked and the amount of minutes users slept in a day.

**3. Steps distribution over days of the week**

<img src="https://www.kaggleusercontent.com/kf/235179192/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..XyhqfU0QeReDEoNmzQoH8Q.c5HDUUpuBf6YxuKMdEMsEIXishkq17c-0erJWrG-3FWiHTtnamu4tXK9QbYHFQ0uDLYybiQeX4zRmKXJIOt29w3KXn5rKonwKq5Qq72WaMC8MwN1SMWNwc4XBqzT_u6rIB8rEthRNl9GVVoyVGbJIbks43eZ9YrApGhmOK4teVovE_ueakzpy79IIvMt19_HKILNBbDOITlZye4MTHE0SgMjUNm6KPDafVIUNxm6PWtcLCTM7p8alxklgQxpnjDxPBoLuUAi_SfnGh6Dw_0kyar-xuGt0KsJ9a6Ri68BroT21vofY8ISA8gCd9D4dnNY-c4BqNKzERUhyvmOh4tT-VAZH-2_q7a0Y9DjTzm0aYHyrQSPL-9iV8SfyiI8kMmptyYYLnJ67Ojdxz66hJ5X8MYkDdV0CgCfN6zaXAt_MF2WcDkzemZHnvIrsSr5vYhfxmVmlU5Q1giRBtk3wNtmrUThfPP3t9utZyXqvuZCJgdEkd69E_WquD2Q7VRFISRHz1JZLQuuCrk0rkGmtwe4GHQ_HRkbOhSFcYey441XrbYywluMc-L_ZJnI0nKhxcxt1It7HqtkeUMkuiItyr13nzTE37yJAy5pNKg8YgHG-Y6k4v8juSzwN3XrYYOx8PPSXf9QBIjXKbvX-q74OxS6nA.78spGWXnLcDGxAT2kV230A/__results___files/__results___37_0.png" alt="Viz Image" width="400" height="450">

Users walk the daily recommended count of 7500 steps on all the days except for Sunday.

**4. Sleep distribution over days of the week**

<img src="https://www.kaggleusercontent.com/kf/235179192/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..XyhqfU0QeReDEoNmzQoH8Q.c5HDUUpuBf6YxuKMdEMsEIXishkq17c-0erJWrG-3FWiHTtnamu4tXK9QbYHFQ0uDLYybiQeX4zRmKXJIOt29w3KXn5rKonwKq5Qq72WaMC8MwN1SMWNwc4XBqzT_u6rIB8rEthRNl9GVVoyVGbJIbks43eZ9YrApGhmOK4teVovE_ueakzpy79IIvMt19_HKILNBbDOITlZye4MTHE0SgMjUNm6KPDafVIUNxm6PWtcLCTM7p8alxklgQxpnjDxPBoLuUAi_SfnGh6Dw_0kyar-xuGt0KsJ9a6Ri68BroT21vofY8ISA8gCd9D4dnNY-c4BqNKzERUhyvmOh4tT-VAZH-2_q7a0Y9DjTzm0aYHyrQSPL-9iV8SfyiI8kMmptyYYLnJ67Ojdxz66hJ5X8MYkDdV0CgCfN6zaXAt_MF2WcDkzemZHnvIrsSr5vYhfxmVmlU5Q1giRBtk3wNtmrUThfPP3t9utZyXqvuZCJgdEkd69E_WquD2Q7VRFISRHz1JZLQuuCrk0rkGmtwe4GHQ_HRkbOhSFcYey441XrbYywluMc-L_ZJnI0nKhxcxt1It7HqtkeUMkuiItyr13nzTE37yJAy5pNKg8YgHG-Y6k4v8juSzwN3XrYYOx8PPSXf9QBIjXKbvX-q74OxS6nA.78spGWXnLcDGxAT2kV230A/__results___files/__results___39_0.png" alt="Viz Image" width="400" height="450">

The sleeptime of the users is always less than the recommended 8 hours (480 minutes) of sleep.

**5. Sedentary minutes vs minutes asleep**

<img src="https://www.kaggleusercontent.com/kf/235179192/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..XyhqfU0QeReDEoNmzQoH8Q.c5HDUUpuBf6YxuKMdEMsEIXishkq17c-0erJWrG-3FWiHTtnamu4tXK9QbYHFQ0uDLYybiQeX4zRmKXJIOt29w3KXn5rKonwKq5Qq72WaMC8MwN1SMWNwc4XBqzT_u6rIB8rEthRNl9GVVoyVGbJIbks43eZ9YrApGhmOK4teVovE_ueakzpy79IIvMt19_HKILNBbDOITlZye4MTHE0SgMjUNm6KPDafVIUNxm6PWtcLCTM7p8alxklgQxpnjDxPBoLuUAi_SfnGh6Dw_0kyar-xuGt0KsJ9a6Ri68BroT21vofY8ISA8gCd9D4dnNY-c4BqNKzERUhyvmOh4tT-VAZH-2_q7a0Y9DjTzm0aYHyrQSPL-9iV8SfyiI8kMmptyYYLnJ67Ojdxz66hJ5X8MYkDdV0CgCfN6zaXAt_MF2WcDkzemZHnvIrsSr5vYhfxmVmlU5Q1giRBtk3wNtmrUThfPP3t9utZyXqvuZCJgdEkd69E_WquD2Q7VRFISRHz1JZLQuuCrk0rkGmtwe4GHQ_HRkbOhSFcYey441XrbYywluMc-L_ZJnI0nKhxcxt1It7HqtkeUMkuiItyr13nzTE37yJAy5pNKg8YgHG-Y6k4v8juSzwN3XrYYOx8PPSXf9QBIjXKbvX-q74OxS6nA.78spGWXnLcDGxAT2kV230A/__results___files/__results___41_1.png" alt="Viz Image" width="400" height="450">

There is a negative correlation between the sedentary minutes and the minutes asleep. This shows that higher the sedentary minutes, lower is the sleep time.

**Relation between time of the day, day of the week, active time**

<img src="https://github.com/shivani8136/Bellabeat-Smart-Device-Data-Analysis/blob/main/images/Heatmap%20image.png" alt="Viz Image">

We can see that the users are more active between 7am and 6pm. Most of the walking takes place before lunch time from 11am to 12pm and in the evenings between 4pm and 6pm.


### Recommendations

Based on my analysis of the smart device data, I would provide the following recommendations to the product team at Bellabeat.

1. **Bedtime notification**: Users will have to set a sleep goal which would include the user's desired bedtime and duration of sleep. Users will receive a reminder 15 minutes prior to the preset bedtime and will also have an wake up alarm set based on the preset duration of sleep.

2. **Mandatory weight information update**: Users will have to enter their weight information mandatorily on a daily basis. This will help the users track their weight loss/maintenance journey effectively.

3. **Notifications to reduce sedentary time**: Users will receive a notification if they are found to be sedentary for a continuous period of time during the day.

