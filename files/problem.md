# Problem Background

## Introduction

<span style="color:red">TODO: Intro for HRfH</span>


## Task 1 Description: Simulation with Treatment Dynamics

The task is to revise a simulation using the following simplified information:

- Patient ID
- Days (1 to 180)
- Pain Measurements (scaled 0-10)

Output Requirements
Pain measurements for each patient over 180 days.


## Task 2 Description: Predicting Pain Measurements and Optimizing Sampling Frequency

### Task Overview
Imagine you have data on 1,000 patients, each with daily pain measurements recorded over 180 days. However, in the real world, collecting patient-reported outcomes can be expensive and time-consuming. Your mission is to forecast patients’ final 30 days of pain with high accuracy—while also minimizing the number of extra data points you request.

### The Data
1. Training Set: Full 180-day pain trajectories for 800 patients. Use these to build and fine-tune your models.
2. Test Set (For result evaluation): 200 patients, for which you’ll initially see only the first 7–14 days of data.

### The Twist: Adaptive Data Retrieval
Before generating your final predictions on days 151–180, you have the option to retrieve additional daily measurements from days 15–150 for each patient—but at a cost. Each requested data point adds to your overall penalty.


### The Challenge
1. Train on the 800 fully observed patients.
2. For each of the 200 test patients, request (or skip) selected days from the unobserved portion of their record (days 15–150).
3. Forecast pain levels for the final 30 days (days 151–180).

### Evaluation
You will be scored on two factors:

1. Predictive Accuracy: How close your forecasts are to the true pain values (e.g., via Mean Absolute Error).
2. Data Cost: The number of extra data points you requested.
We’ll combine these into a single score, penalizing overuse of data queries. Low error with minimal requests = the best score!
