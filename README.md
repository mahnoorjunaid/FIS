Enhancing Credit Risk Assessment via Fuzzy Inference Systems (FIS)
==================================================================

📌 Project Overview
-------------------

This project addresses the limitations of traditional binary credit scoring models (like Logistic Regression and XGBoost) by implementing a **Mamdani-type Fuzzy Inference System**.

Unlike standard models that use "hard" numerical thresholds, this FIS uses **linguistic uncertainty** and **overlapping membership functions** to assess creditworthiness. This approach is specifically designed for the FinTech sector to improve financial inclusion for "thin-file" borrowers while maintaining high sensitivity to default risks.

🚀 Key Features
---------------

*   **Linguistic Modeling**: Converts crisp data (e.g., "Income: $50,000") into fuzzy concepts (e.g., "Moderate Income").
    
*   **Expert-Derived Rule Base**: Uses 25 human-readable "If-Then" rules, making the AI's decision-making process transparent and regulatory-compliant.
    
*   **Data-Driven Calibration**: Includes a rule-weighting mechanism that adjusts the importance of specific rules based on historical default patterns.
    
*   **High Recall (Default Detection)**: Specifically optimized to minimize Type II errors (missing a defaulter), achieving a recall rate of **83.33%**.
    

🛠️ System Architecture
-----------------------

The pipeline consists of the following stages:

1.  **Data Acquisition**: German Credit Dataset integrated with simulated FinTech alternative data.
    
2.  **Preprocessing**: Median/Mode imputation, Min-Max normalization, and **SMOTE** for handling class imbalance.
    
3.  **Feature Selection**: Hybrid approach using **Fisher Score** and **Recursive Feature Elimination (RFE)** to select the 8 most critical risk drivers.
    
4.  **Fuzzification**: Mapping features to Gaussian and Triangular membership functions.
    
5.  **Inference Engine**: Firing the rule base to evaluate the degree of risk.
    
6.  **Defuzzification**: Using the **Centroid method** to produce a final Probability of Default (PD) score.
    

📊 Performance Comparison
-------------------------

Tested against industry-standard baselines, the FIS model demonstrates superior risk sensitivity:

**MetricProposed FISLogistic RegressionXGBoostRecall (Sensitivity)0.8333**0.66670.5667**Type II Error0.1667**0.33330.4333**AUC-ROC**0.7520.7880.811

_Note: While XGBoost has a higher overall AUC, the FIS is more effective at identifying actual defaulters, which is critical for bank stability._

💻 Tech Stack
-------------

*   **Language**: Python 3.10
    
*   **Environment**: Google Colab / Jupyter Notebook
    
*   **Primary Libraries**:
    
    *   scikit-fuzzy: For FIS construction and membership function mapping.
        
    *   scikit-learn: For feature selection (RFE), SMOTE, and baseline comparisons.
        
    *   pandas & numpy: For data manipulation.
        
    *   matplotlib: For visualizing fuzzy sets and membership overlaps.
        

📖 How to Use
-------------

1.  **Input**: Provide borrower data (Checking account status, Credit history, Income level, etc.).
    
2.  **Process**: The system fuzzifies the inputs and applies the 25 linguistic rules.
    
3.  **Output**:
    
    *   **PD Score**: A value between 0 and 1.
        
    *   **Classification**: Approved (PD < 0.40) or Rejected (PD ≥ 0.40).
        
    *   **Explanation**: A linguistic justification for the score (e.g., "Risk is High due to Low Duration and Critical Account Status").
        

⚖️ License & Attribution
------------------------

**Author:** Mahnoor Junaid

**Affiliation:** FAST National University of Computing and Emerging Sciences, Islamabad.

_This project was developed as a research initiative into FinTech and Financial Inclusion._
