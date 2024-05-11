# Efficiency Insight - Energy Consumption Anomaly Detection and Interactive Visualization for Educational Buildings

This exploratory project overview is a class group project for `Team 086` in Georgia Tech's CSE 6242 Data and Visual Analytics, a graduate subject offered as part of [OMSA](https://pe.gatech.edu/degrees/analytics) and [OMSCS](https://omscs.gatech.edu/) programs. For more details on the class, please visit the [CSE6242](https://omscs.gatech.edu/cse-6242-data-and-visual-analytics) website. The CSE 6242 class, taught by Prof Polo Chau in Fall 2023, has the following course goals;
> - Learn **visual** and **computation** techniques and tools, for typical data types.
> - Learn how to **complement** each kind of method.
> - Work on **real datasets and problems**.
> - Learn **practical** know-how (useful for jobs, and research) through significant hands-on programming assignments.

Disclaimer: The views and opinions expressed in this project are those of the authors and do not necessarily reflect the views or positions of Georgia Tech.

## Background

Worldwide, buildings are responsible for approximately 30% of energy consumption and about 26% of energy-related emissions [^1]. With the expansion of global floor space and heightened regulatory focus on energy efficiency, the significance of reducing energy consumption cannot be overstated. Lowering energy use is crucial not only for mitigating climate change on a broad scale but also for reducing energy costs at the individual level.

## Project Motivation
Numerous studies have focused on enhancing the accuracy of anomaly detection through the development of machine learning algorithms. Nevertheless, a significant obstacle to scaling building energy efficiency is the challenge of ensuring that key stakeholders fully understand building operational patterns and potential improvement opportunities. This challenge often stems from the end-users' limited time and technical expertise. To address this issue, our goal was to bridge the gap by making machine learning insights more accessible to end-users through interactive visualizations.

### Project Overview


![Figure 1: Updated methodology overview](https://github.com/iamkevk/DVA_6242/assets/66114561/1be6d786-7e1f-43f3-a429-5d5500ee906e)*Figure 1: Updated methodology overview*

- **Data source**: The Building Data Genome Project 2 dataset [^2], ***is an open data set of 3,053 energy meters from 1,636 non-residential buildings with a range of two full years (2016 and 2017) at an hourly frequency (17,544 measurements per meter resulting in approximately 53.6 million measurements)***. 
- **Data Pre-processing**: Handled missing values, feature engineering, Categorical encoding, and training-test split.
- **Model Development**: Model Training with LightGBM on the pre-processed & feature-engineered dataset. Parameters for the LightGBM model are defined with the objective set to “huber” with alpha = 0.3 to tone down the influence of outliers, tree max depth & regularization factors are also set to avoid overfitting after several hundred epochs.
- **Anomaly Detection**: A threshold for anomalies is calculated from the error distribution in the training data. Anomalies are flagged in the data based on this threshold.  A rule-based method is implemented to detect frozen sensor readings.
- **Interactive Visualization**: Key components of visualization include:
- - Energy consumption history and count of anomalous readings, including two types of anomalies (static meter reading, high prediction error) for groups of and individual buildings and sites through use of filters.
  - 


## References
[^1]: [IEA Tracking Buildings](https://www.iea.org/energy-system/buildings#tracking)
[^2]: [The Building Data Genome Project 2](https://www.nature.com/articles/s41597-020-00712-x)

