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
This task involves two steps:

1. Train a Model

Input data: Pain measurements from 800 patients, each with:
- Patient ID
- 180 days of pain measurements (scaled from 0-10).

Objective:
Train a predictive model to take 30 days of pain measurement data as input and accurately predict the remaining 150 days of measurements for each patient.

2. Optimize Measurement Frequency

Design an algorithm to reduce the frequency of measurements while ensuring no significant change points in pain trajectories are missed.
Change points: Critical moments where pain measurements exhibit noticeable increases or decreases.

Analyze the predicted trajectories to identify the key change points where pain states shift significantly. Develop an algorithm to reduce measurement frequency while preserving these critical points. Ensure the algorithm achieves a balance between fewer measurements and the retention of clinically significant trajectory changes.

### Deliverables
- A predictive model that can:
  - Accept 30 days of input data.
  - Accurately predict the remaining 150 days of pain measurements.

- An optimized measurement strategy that:
  - Reduces the frequency of pain measurements.
  - Preserves key trajectory change points for clinical analysis.
