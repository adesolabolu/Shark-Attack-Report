# Shark-Attack-Report
This project explores the world of shark attacks through data analysis. We'll uncover patterns in location, time, species, and more to understand these encounters better.

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaningpreparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#resultsfindings)

### Project Overview

---

This project delves into the world of shark-human interactions by analyzing data on reported shark attacks. Our goal is to gain a deeper understanding of these occurrences through a data-driven approach.

### Data Sources

The project leverages a public dataset on shark attack which include;
- "attack.csv" file, containing detailed information about the shark attacks


### Tools
  - Excel - Univariate Analysis
  - Power Query - Data Cleaning and Preparation
  - PowerBI - Data Visualization

### Data Cleaning/Preparation

In the data preparation phase, we performed the following tasks:
1. Data loading and inspection
2. Handling missing values
3. Text Analysis
4. Data cleaning and formatting

### Exploratory Data Analysis

EDA involved exploring the datasets to answer key questions such as:

- Total Attacks
- Total Fatal Attacks
- Attack Frequency by Time of Day
- Countries with highest number of shark attack
- Location with highest number of shark attack
- Area with highest number of shark attack
- Shark specie with highest number of shark attack
- Shark attack trend by Year
- Most Injured Body Parts from shark attacks
- Shark attack by type

### Data Analysis

Here's some of the code I used for my analysis;
For text analysis of the Body Part column, I used a conditonal column on Power Query;
```F#
 #"Added Conditional Column" = Table.AddColumn(#"Replaced Value2", "Body Part", each if Text.Contains([Injury], "hand") then "Hand" else if Text.Contains([Injury], "leg") then "Leg" else if Text.Contains([Injury], "thigh") then "Leg" else if Text.Contains([Injury], "Thigh") then "Leg" else if Text.Contains([Injury], "Hand") then "Hand" else if Text.Contains([Injury], "Foot") then "Foot" else if Text.Contains([Injury], "foot") then "Foot" else if Text.Contains([Injury], "arm") then "Hand" else if Text.Contains([Injury], "finger") then "Finger" else if Text.Contains([Injury], "knee") then "Leg" else if Text.Contains([Injury], "shin") then "Leg" else if Text.Contains([Injury], "FATAL") then "Death" else if Text.Contains([Injury], "forearm") then "Hand" else if Text.Contains([Injury], "calf") then "Leg" else if Text.Contains([Injury], "Calf") then "Leg" else if Text.Contains([Injury], "Fatal") then "Death" else if Text.Contains([Injury], "fatal") then "Death" else if Text.Contains([Injury], "toes") then "Foot" else if Text.Contains([Injury], "Torso") then "Abdomen" else if Text.Contains([Injury], "buttocks") then "Buttocks" else if Text.Contains([Injury], "Hand") then "Hand" else if Text.Contains([Injury], "toe") then "Foot" else if Text.Contains([Injury], "Legs") then "Leg" else if Text.Contains([Injury], "Buttocks") then "Buttocks" else if Text.Contains([Injury], "Foot") then "foot" else if Text.Contains([Injury], "Leg") then "Leg" else if Text.Contains([Injury], "Ankle") then "Foot" else if Text.Contains([Injury], "ankle") then "Foot" else if Text.Contains([Injury], "shoulder") then "Hand" else if Text.Contains([Injury], "Chest") then "Chest" else if Text.Contains([Injury], "chest") then "Chest" else if Text.Contains([Injury], "wrist") then "Hand" else if Text.Contains([Injury], "heel") then "Foor" else if Text.Contains([Injury], "elbow") then "Hand" else if Text.Contains([Injury], "Face") then "Face" else if Text.Contains([Injury], "Elbow") then "Elbow" else if Text.Contains([Injury], "Arm") then "Hand" else if Text.Contains([Injury], "No injury") then "N/A" else if Text.Contains([Injury], "Heel") then "Foot" else if Text.Contains([Injury], "hip") then "Leg" else if Text.Contains([Injury], "torso") then "Abdomen" else if Text.Contains([Injury], "Shoulder") then "Hand" else if Text.Contains([Injury], "Buttock") then "Buttock" else if Text.Contains([Injury], "head") then "Head" else if Text.Contains([Injury], "ribs") then "Abdomen" else if Text.Contains([Injury], "back") then "Back" else if Text.Contains([Injury], "feet") then "Foot" else if Text.Contains([Injury], "face") then "Face" else if Text.Contains([Injury], "neck") then "Face" else if Text.Contains([Injury], "Hip") then "Leg" else if Text.Contains([Injury], "Toe") then "Foot" else if Text.Contains([Injury], "forearm") then "Hand" else if Text.Contains([Injury], "knee") then "Leg" else if Text.Contains([Injury], "Knee") then "Leg" else if Text.Contains([Injury], "Feet") then "Foot" else if Text.Contains([Injury], "eye") then "Face" else if Text.Contains([Injury], "Finger") then "Finger" else if Text.Contains([Injury], "Shin") then "Foot" else if Text.Contains([Injury], "thumb") then "Finger" else if Text.Contains([Injury], "Wrist") then "Hand" else if Text.Contains([Injury], "Head") then "Head" else if Text.Contains([Injury], "Toes") then "Foot" else if Text.Contains([Injury], "Hamstring") then "Leg" else if Text.Contains([Injury], "cheek") then "Face" else if Text.Contains([Injury], "Fingers") then "Finger" else if Text.Contains([Injury], "Minor") then "N/A" else if Text.Contains([Injury], "no injury") then "N/A" else if Text.Contains([Injury], "board broken") then "N/A" else if Text.Contains([Injury], "No detail") then "N/A" else if Text.Contains([Injury], "Stingray") then "N/A" else if Text.Contains([Injury], "Stingray") then "N/A" else if Text.Contains([Injury], "Survived") then "N/A" else if Text.Contains([Injury], "Multiple injuries") then "N/A" else if Text.Contains([Injury], "No details") then "N/A" else if Text.Contains([Injury], "needs investigation") then "N/A" else if Text.Contains([Injury], "Abdomen") then "Abdomen" else if Text.Contains([Injury], "foream") then "Hand" else if Text.Contains([Injury], "Left eg") then "Leg" else if Text.Contains([Injury], "Groin") then "Abdomen" else if Text.Contains([Injury], "Cheek") then "Face" else if Text.Contains([Injury], "palm") then "Hand" else if Text.Contains([Injury], "tendon") then "Leg" else if Text.Contains([Injury], "am") then "Hand" else if Text.Contains([Injury], "Tooth") then "Face" else if Text.Contains([Injury], "Facial") then "Face" else if Text.Contains([Injury], "Thumb") then "Fingers" else if Text.Contains([Injury], "buttock") then "Buttock" else if Text.Contains([Injury], "Penis") then "Abdomen" else if Text.Contains([Injury], "calves") then "Leg" else if Text.Contains([Injury], "Back") then "Back" else if Text.Contains([Injury], "Quadriceps") then "Hand" else "N/A"),
```
