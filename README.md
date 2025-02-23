# Analysis of Forest Fires using Bayesian Networks

This repository contains a comprehensive project that applies Bayesian Network modeling to analyze forest fire risk using meteorological data. Developed by Kiana Alian, Luyao Ma, and Arnab Mukhopadhyay as part of our Master’s Degree in Artificial Intelligence at the University of Bologna, this project leverages data from the Forest Fires dataset (collected from Montesinho Natural Park in Portugal) to explore the complex relationships between environmental factors and wildfire behavior.

## Overview

Forest fires are influenced by a variety of interrelated meteorological and environmental variables. In this project, we focus on capturing these interactions through the use of Bayesian Networks—a class of probabilistic graphical models that represent variables and their conditional dependencies. Our analysis not only aims to predict fire severity by understanding these dependencies but also to compare different model structures to identify the most effective approach for wildfire risk assessment.

## Project Objectives

- **Probabilistic Modeling:** Develop Bayesian Networks to capture the intricate dependencies among key variables such as temperature, humidity, wind speed, and rainfall.
- **Comparative Analysis:** Evaluate four distinct Bayesian Network models:
  - **Custom Bayesian Network (CBN):** A model manually defined based on domain expertise.
  - **Tree Search-Based (TSB) Model:** A model learned using a tree search algorithm.
  - **Hill Climbing with Score-Based (HCSB) Model:** A model optimized using hill climbing with the Bayesian Dirichlet Equivalent Uniform (BDeu) score.
  - **Hill Climbing with Constraint and Score-Based (HCSCB) Model:** A hybrid model that incorporates both score-based and constraint-based optimization.
- **Performance Evaluation:** Measure model performance using metrics such as accuracy, recall, precision, and F1-score to understand the trade-offs between model complexity and predictive capability.

## Methodology

1. **Data Acquisition & Preprocessing:**
   - The Forest Fires dataset from the UCI Machine Learning Repository serves as the primary data source.
   - The dataset includes 12 key attributes: meteorological variables (e.g., temperature, humidity, wind speed, rainfall) and fire weather indices (such as FFMC, DMC, Drought Code, and ISI).
   - Data preprocessing involved binning continuous variables and normalizing the dataset to facilitate effective probabilistic inference.

2. **Model Construction:**
   - **Custom Bayesian Network (CBN):** Built using domain knowledge, this model connects variables such as temperature to surface fuel dryness and humidity to deeper fuel moisture.
   - **Automated Structure Learning:** Implemented using tree search and hill climbing algorithms (both score-based and hybrid methods) via the `pgmpy` library, these models automatically infer the network structure from data.
   - **Parameter Estimation & Inference:** Maximum likelihood estimation is used for parameter learning, and variable elimination is employed for probabilistic inference.

3. **Evaluation & Visualization:**
   - Model performance was rigorously evaluated using standard metrics computed with scikit-learn.
   - Visualization libraries including NetworkX, Seaborn, and Plotly were used to generate graphical representations of the network structures and data insights.

## Results & Conclusion

The experimental analysis revealed that:
- **Automated models excel:** The tree search-based and hill climbing methods (both HCSB and HCSCB) demonstrated superior performance, achieving accuracies of up to 99.04%, while the manually defined CBN model achieved 98.08% accuracy.
- **Comparable Performance:** The similar results between the hill climbing variants suggest that integrating constraints with score-based optimization enhances model interpretability without compromising accuracy.
- **Enhanced Understanding:** These findings highlight the effectiveness of advanced Bayesian Network techniques in capturing complex interdependencies, ultimately contributing to more accurate wildfire risk assessments and providing valuable insights for fire management strategies.

## External Resources & References

- **Dataset:** [UCI Forest Fires Dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/forest-fires/forestfires.csv)
- **Key References:**
  - Pacheco, F. et al. (2015). "Assessing the probability of wildfire occurrence in Portugal using a Bayesian Network approach." *Environmental Management*, 55(2):397–410.
  - Cortez, P. and Morais, A.D.J.R. (2007). "A data mining approach to predict forest fires using meteorological data." *New Trends in Artificial Intelligence*, 3:512–523.

## How to Run

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/forest-fire-bayesian-networks.git
   cd forest-fire-bayesian-networks
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Execute the Analysis:**
   - Run the Jupyter Notebook or Python scripts provided in the repository to reproduce the analysis and visualize the results.
   ```bash
   jupyter notebook Analysis_of_Forest_Fires.ipynb
   ```

## Contributions

Contributions, suggestions, and improvements are highly welcome. Please feel free to open issues or submit pull requests.
