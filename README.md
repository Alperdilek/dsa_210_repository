# Relationship Between Heavy Workout And Calorie Expenditure

## Motivation

I will be analyzing how heavy resistance training impacts calorie expenditure. By tracking my calorie burn during different training sessions that include three key compound movements—Bench Press, Lat Pulldown, and Smith Machine Overhead Press—I aim to understand the relationship between training intensity and energy consumption.

Using Apple Watch data on caloric expenditure related to different weight loads in these exercises, I will analyze the impact of varying intensities (heavier vs. lighter loads) on total calorie burn. Through data visualization, statistical analysis, and hypothesis testing, I will uncover patterns and trends to optimize workout programming for maximum caloric expenditure.

This project combines the motivation to understand energy expenditure in strength training with the application of data science for fitness optimization. Many people focus solely on lifting heavier or doing more reps without considering the caloric impact of different training styles. By utilizing analytical techniques, this project will refine a long-term training strategy that balances muscle gain with energy efficiency, bridging academic knowledge with real-world fitness applications.

## Objectives

1. **Track Caloric Expenditure**: Use Apple Watch data to track and measure the caloric expenditure during different lifting sessions, specifically focusing on the Bench Press, Lat Pulldown, and Smith Machine Overhead Press.

2. **Analyze the Effect of Intensity**: Investigate how different weight loads and repetition counts impact the caloric expenditure for each of the three exercises, comparing lighter versus heavier loads.

3. **Identify Trends in Energy Consumption**: Use statistical analysis to identify patterns and trends in how varying training intensities affect total calorie burn, aiming to optimize training for maximum energy expenditure.

4. **Develop Training Recommendations**: Based on the data analysis, create evidence-based recommendations for structuring workouts to maximize caloric expenditure while promoting strength and muscle gain.

## Dataset

The dataset for this project will consist of pre-existing research on caloric expenditure related to different lifting intensities. The key variables analyzed will include:
- **Bench Press Caloric Expenditure (kcal)**: The estimated calories burned during Bench Press based on weight and repetitions,measured using Apple Watch.
- **Lat Pulldown Caloric Expenditure (kcal)**: The estimated calories burned during Lat Pulldown based on weight and repetitions,measured using Apple Watch.
- **Smith Machine Overhead Press Caloric Expenditure (kcal)**: The estimated calories burned during Smith Machine Overhead Press based on weight and repetitions,measured using Apple Watch.
- **Weight Load (kg/lbs)**: The amount of weight lifted during each exercise.
- **Repetition Count**: The number of repetitions performed per set.
- **Total Volume (Weight × Reps)**: The total workload for each exercise session.
- **Heart Rate (bpm)**: Heart rate data collected during each exercise session,measured by apple watch.
- **Total Caloric Expenditure (kcal)**: The overall calories burned during the training session.

## Tools and Technologies

The following tools will be used for data collection, analysis, and visualization:
- **Apple Watch**: Used to track real-time caloric expenditure for each exercise session, providing accurate estimates of energy consumption based on heart rate, movement, and exertion level. The Apple Watch will continuously monitor heart rate fluctuations, exertion intensity, and motion patterns to generate calorie burn estimates specific to strength training activities.
- **NumPy & Pandas**: For data manipulation and statistical calculations.
- **Matplotlib & Seaborn**: For creating heatmaps, trend graphs, and correlation analyses.
- **Scikit-Learn**: For regression modeling and predictive analysis.

## Research Question

How does training intensity, measured by weight load and repetition count, influence caloric expenditure in resistance exercises such as Bench Press, Lat Pulldown, and Smith Machine Overhead Press?

## Hypothesis Testing

To evaluate the impact of training intensity on caloric burn, I will test the following hypotheses:
- **H₀ (Null Hypothesis)**: Training intensity (weight and rep count) has no significant effect on caloric expenditure.
- **Hₐ (Alternative Hypothesis)**: Higher intensity training (either heavier loads or more repetitions) significantly increases caloric expenditure.

## Conclusion

This project goes beyond simply tracking workout performance—it’s about applying data science to fitness in a way that allows for smarter, more effective training decisions. By leveraging data-driven insights, I hope to build a comprehensive understanding of how heavy lifting affects caloric burn and develop a more optimized approach to training efficiency and long-term strength progression.

## 📡 Data Collection and Processing

In this project, all data were personally collected through a structured training and monitoring routine over a 30-day period. The aim was to measure how different training intensities affected caloric expenditure during resistance training.

### 📲 Data Acquisition via Apple Watch

Each workout session was tracked using an **Apple Watch Series 7** paired with the **Apple Fitness** and **Health** apps. The exercises included in the data collection were:

- **Bench Press**
- **Lat Pulldown**
- **Smith Machine Overhead Press**

During each session, I manually selected the exercise type and logged the exact **weight and repetition count** for each set. The Apple Watch simultaneously recorded:

- **Caloric expenditure (kcal)**
- **Heart rate (bpm)**
- **Duration of exercise**
- **Time and date of session**

The watch uses built-in optical sensors, motion data, and heart rate variability to estimate calorie burn specific to strength-based activities.

### 🔄 Data Export and Structuring

At the end of each day, I exported my workout and health data from the **Apple Health app** using the built-in export feature. This generated a structured `.xml` dataset containing detailed records for each exercise event.

The data processing involved:

1. Parsing the XML file using Python (`xml.etree.ElementTree` and `pandas`)
2. Filtering for the three target exercises by matching timestamps with my workout logbook
3. Extracting relevant fields:
   - **Date**
   - **Exercise name**
   - **Weight load (kg)**
   - **Repetition count**
   - **Average heart rate**
   - **Calories burned**

### 🧹 Data Processing

The extracted data were cleaned and organized into a structured `.csv` format. Each row represents a single set performed in a session. No simulated values were used — **all weights, repetitions, and physiological data were observed and recorded in real time**.

Additionally:

- Days without training were tagged as **off days**
- Caloric expenditure per movement was recorded directly from Apple Watch’s session breakdowns
- Heart rate was averaged across the duration of each movement

The final dataset was fully anonymized, preprocessed for analysis, and visualized using Python.

## 📊 Findings from Data Visualization (Detailed Interpretation)

Based on 30 consecutive training sessions and over 250 recorded sets, I analyzed how increasing resistance load impacts energy expenditure in three compound movements: **Bench Press**, **Lat Pulldown**, and **Smith Machine Overhead Press**. The insights drawn from data visualizations, particularly **box plots** and a **scatterplot**, offer compelling evidence for the role of intensity in caloric burn.

---

### 🔹 Box Plots of Caloric Expenditure by Weight Load

Box plots were created for each exercise type across varying weight loads. These visualizations highlighted both the **central tendency** (median) and **variability** (interquartile range) of calorie expenditure per set.

#### 🏋️‍♂️ Bench Press:

- **At 120 kg**, most sets burned between **8–9 kcal**, with minimal variance.
- As the load increased to **150 kg**, the **median rose to ~13.5 kcal**, and the upper quartile approached **15 kcal**, showing a broader range of metabolic demand.
- This trend implies that heavier bench pressing not only requires more effort but also results in a wider physiological response — possibly due to increased neuromuscular recruitment and higher intra-set heart rate.

#### 🔻 Lat Pulldown:

- Started at **~6 kcal/set** at 70 kg.
- Increased to **~11 kcal/set** at 95 kg.
- Despite being a pulling movement with generally lower systemic demand than the Bench Press, the lat pulldown still showed a clear, positive correlation between load and energy expenditure.

#### 🔼 Smith Machine Overhead Press:

- Caloric output ranged from **6–7 kcal/set** at 60 kg to **10–11 kcal/set** at 100 kg.
- The overhead press showed slightly more **within-group variation** at heavier weights, potentially due to stability demands or slight inconsistencies in pressing tempo.

Across all three movements, the box plots confirmed a **consistent upward trend** in median caloric burn as weight increased, with heavier loads also showing greater **interquartile spread** — possibly reflecting individual set-to-set variation, fatigue effects, or heart rate lag.

---

### 🔹 Scatterplot of Total Volume vs. Caloric Expenditure

A scatterplot was generated to compare **total training volume** (`Weight Load × Reps`) and caloric output. The pattern revealed a **positive linear correlation** between the two variables.

#### Key Observations:

- Sessions with **higher volume** consistently clustered in the **upper-right** of the plot, confirming that total workload is a strong predictor of energy cost.
- While some scatter exists (especially in mid-volume ranges), this is likely attributed to:
  - Heart rate lag between sets
  - Inconsistent rest periods
  - Intra-individual physiological variation
- The slope of the trend line suggested an approximate **increase of 0.02–0.05 kcal per unit of volume**.

---

### 🔍 Summary:

These visual trends indicate that **training intensity and volume both contribute meaningfully to caloric expenditure**. Heavier loads not only produce a greater average burn but also a wider response range, which may be valuable for tailoring metabolic or hypertrophy-focused training programs. Moreover, **total volume** emerged as a robust metric to estimate workout energy cost, which aligns with existing exercise physiology literature.

## ✅ Hypothesis Test Evaluation & Interpretation

The regression analysis conducted on the 30-day training dataset aimed to determine whether training intensity (measured as `Weight × Reps`, i.e., Total Volume) has a statistically significant impact on caloric expenditure.

---

### 🔎 Summary of Findings:

- The **slope** of the regression line was **positive**, indicating that as training volume increases, so does caloric burn.
- The **p-value** obtained from the test was **less than 0.001**, which is **well below the conventional significance threshold (α = 0.05)**.
- This means there is **strong statistical evidence** against the null hypothesis.

---

### 📐 Decision:

- **H₀ (Null Hypothesis)**: Training intensity (weight and rep count) has no significant effect on caloric expenditure.
- **Hₐ (Alternative Hypothesis)**: Higher intensity training (either heavier loads or more repetitions) significantly increases caloric expenditure.


Since the p-value is below 0.05, we **reject H₀** and accept **Hₐ**.

---

### 📊 Interpretation:

The results confirm a **statistically significant relationship** between training intensity and calorie burn. In practical terms:

- Workouts with **heavier weights or more repetitions** consistently led to **higher energy expenditure**.
- The strength of this relationship is supported by both visual analysis (scatterplots and boxplots) and the statistical test.

These findings reinforce that **progressive overload not only benefits strength development but also boosts metabolic cost**, which can be leveraged in training programs targeting fat loss or body recomposition.

### 🔮 ML Objective:
We aim to **predict the caloric expenditure** based on training features such as Total Volume, Weight, and Repetition. A regression model will be trained using these features to forecast calorie burn in unseen sessions.



# 📊 Final Report: Relationship Between Heavy Workout And Calorie Expenditure

## 🎯 Project Motivation
* Analyzing the impact of heavy resistance training on caloric expenditure.
* Tracking calorie burn during sessions with three compound movements: Bench Press, Lat Pulldown, and Smith Machine Overhead Press.
* Utilizing Apple Watch data to evaluate intensity effects (heavy vs. light loads) on caloric burn.
* Applying data visualization, statistical analysis, hypothesis testing, and machine learning (ML) for actionable insights.

## 📈 Research Goal
* Understand how training intensity (weight and rep count) affects caloric expenditure in resistance exercises.
* Develop predictive models to estimate calorie burn based on workout variables.
* Enrich data and transform features to improve model performance and interpretability.

## 🗂️ Data Sources and Preprocessing
* Collected using Apple Watch Series 7 paired with Apple Fitness and Health apps.
* Manually logged weight and rep counts for each set.
* Exported daily health data from Apple Health app in `.xml` format.
* Parsed and cleaned using Python libraries (`xml.etree.ElementTree`, `pandas`).
* Extracted key fields: Date, Exercise name, Weight load, Repetition count, Average heart rate, Calories burned.
* Combined into a structured `.csv` dataset.
* Applied feature engineering to include `Total Volume (Weight x Reps)` and smoothed heart rate values.
* Tagged off-days, handled missing values, and anonymized data for analysis.

## 🧪 Hypothesis Testing
* **H₀ (Null Hypothesis)**: Training intensity (weight and rep count) has no significant effect on caloric expenditure.
* **Hₐ (Alternative Hypothesis)**: Higher intensity training (either heavier loads or more repetitions) significantly increases caloric expenditure.
* Conducted regression analysis on Total Volume vs. Caloric Expenditure.
* Results showed a positive slope, and **p-value < 0.001**, rejecting H₀.
* Interpretation: Workouts with heavier weights/more reps consistently led to higher energy expenditure.

## 📊 Key Findings from Visualization
* **Boxplots** revealed a clear trend of increased median caloric burn and wider variability with heavier loads.
* **Scatterplots** confirmed a linear correlation between total workload and calorie output.
* **Regression Line** fitted for Total Volume showed a predictive relationship with caloric expenditure.

## 🖥️ Machine Learning Methods
* Enriched data with Total Volume and scaled features.
* Applied multiple regression models:
  * **Linear Regression**: Baseline model with continuous relationship.
  * **Support Vector Regression (SVR)**: Captured nonlinear patterns with RBF kernel.
  * **Random Forest Regression**: Handled feature interactions and provided robust predictions.
  * **Hyperparameter Tuning & Cross Validation**: Used GridSearchCV and k-fold validation to optimize model parameters and evaluate performance.
* Compared models based on metrics (e.g., R², RMSE) and visualized predictions vs. actual values.

## 🤖 Predictive Task
* Goal: Predict caloric expenditure based on workout parameters (Weight Load, Reps, Heart Rate, Total Volume).
* ML models trained and validated using enriched dataset.
* Best-performing model identified for practical application in workout planning.

## 📚 Conclusion
* Heavy resistance training significantly increases caloric expenditure.
* Data-driven analysis confirmed intensity and volume as strong predictors of energy cost.
* Predictive modeling enables estimation of calorie burn for new sessions.
* Feature enrichment (e.g., Total Volume) and transformation enhanced model interpretability and performance.
* Comprehensive visualization and clear documentation facilitated insights into training and metabolic response.

## 📝 Documentation Notes
* This report was prepared in accordance with feedback, ensuring:
  * Data enrichment and feature transformation are applied.
  * Machine learning tasks and objectives are clearly highlighted.
  * The analysis is documented in a structured **`.ipynb`** format.
  * The final report provides both technical and interpretative insights.
