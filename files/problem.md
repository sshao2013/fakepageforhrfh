# Problem Background

## Introduction

<span style="color:red">TODO: Intro for HRfH</span>


## Task 1 Description: Simulation with Treatment Dynamics

### Task Overview
In this challenge, you’ll build a simulation that generates daily pain measurements for a set of patients over a 180-day period. Unlike a standard static dataset, this simulation should capture treatment effects and day-to-day fluctuations in patient pain levels. The end goal is to produce a realistic synthetic dataset that can be used in subsequent modeling tasks.

### The Data
Each simulated patient record should contain:

1. Patient ID: A unique identifier for each patient (e.g., 1 through 1,000).
2. Days (1 to 180): A 180-day timeline for each patient.
3. Pain Measurements (0–10 scale): Daily pain scores. You may incorporate:
- Baseline pain levels,
- Potential improvement or worsening over time,
- Random noise or variability,
- Simple or complex “treatment effect” curves (e.g., medication starts, dosage changes, tapering, etc.).

### The Challenge
1. Design/Revise a Simulation:

- Either adapt an existing pain data simulator or build one from scratch.
- Introduce treatment dynamics—for example, a medication might reduce pain after 2 weeks, then fade in effectiveness over the next month.
- Ensure each patient’s trajectory looks diverse yet realistic (no single pattern for all).

2. Incorporate Variability:
- Include random fluctuations to represent day-to-day changes.

3. Output Requirements:
- For each patient (ID 1..N), generate 180 rows of data (one per day) with columns:
  - patid
  - day (1..180)
  - measurement (pain score on a 0–10 scale)


### Evaluation
The result of your simulation will be evaluated by a domain expert. While there is no explicit “forecasting score,” the simulation should meet the following criteria:

1. Maintain Realism: Ensure pain levels remain within the 1–10 range, following logical patterns (e.g., steady improvement or clinically reasonable oscillations).
2. Facilitate Future Tasks: The resulting dataset should be suitable for subsequent analysis tasks.

You are encouraged to be creative in modeling elements with different parameters to enhance the simulator. The ultimate goal is to produce a coherent, flexible simulator that generates daily pain measurements influenced by mock treatments over a 180-day period.

## Task 2 Description: Predicting Pain Measurements and Optimizing Sampling Frequency

### Task Overview
Imagine you have data on 1,000 patients, each with daily pain measurements recorded over 180 days. However, in the real world, collecting patient-reported outcomes can be expensive and time-consuming. Your mission is to forecast patients’ final 30 days of pain with high accuracy—while also minimizing the number of extra data points you request.

### The Data
1. Training Set: Full 180-day pain trajectories for 800 patients. Use these to build and fine-tune your models.
2. Test Set (For result evaluation): 200 patients, for which you’ll initially see only the first 30 days of data.

### The Twist: Adaptive Data Retrieval
Before generating your final predictions on days 151–180, you have the option to retrieve additional daily measurements from days 30–150 for each patient—but at a cost. Each requested data point adds to your overall penalty.


### The Challenge
1. Train on the 800 fully observed patients.
2. For each of the 200 test patients, request (or skip) selected days from the unobserved portion of their record (days 30–150).
3. Forecast pain levels for the final 30 days (days 151–180).

### Evaluation
You will be scored on two factors:

1. Predictive Accuracy: How close your forecasts are to the true pain values (e.g., via Mean Absolute Error).
2. Data Cost: The number of extra data points you requested.
We’ll combine these into a single score, penalizing overuse of data queries. Low error with minimal requests = the best score!
