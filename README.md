## Module 21 Report

## 1. Overview of the Analysis

The purpose of this analysis is to develop a deep learning model capable of predicting the success of funding applicants for the nonprofit organization, Alphabet Soup. By leveraging historical data from over 34,000 previously funded organizations, we aim to build a binary classifier that determines whether future applicants are likely to use the funds effectively. The initial model achieved an accuracy of `73%`, and after optimization, performance improved to `79%`.

## 2. Results

### **Data Preprocessing**

-   **Target Variable:**
    
    -   `IS_SUCCESSFUL` (Binary classification: 1 = Successful, 0 = Unsuccessful)
        
-   **Feature Variables:**
    
    -   Categorical variables: `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `INCOME_AMT`, `ASK_AMT`
        
    -   Numerical variables (after encoding): One-hot encoded categorical features
        
-   **Removed Variables:**
    
    -   `EIN` and `NAME` (Non-beneficial identifiers)
        
    -   `STATUS` (Overwhelmingly skewed towards active organizations)
        
    -   `SPECIAL_CONSIDERATIONS` (Had only one significant category)
        

### **Compiling, Training, and Evaluating the Model**

-   **Neural Network Architecture:**
    
    -   **Layers & Neurons:**
        
        -   First Hidden Layer: **100 neurons**, Relu activation
	        - The first layer has more neurons for better feature extraction.
            
        -   Second Hidden Layer: **30 neurons**, Sigmoid activation.
	        - Additional hidden layers help refine feature learning.
            
        -   Third Hidden Layer: **10 neurons**, Sigmoid activation
	        - Using Sigmoid activation in later layers stabilizes learning and improves convergence.
            
        -   Output Layer: **1 neuron**, Sigmoid activation

            
-   **Model Performance:**
    
    -   **Initial Model Accuracy:** `~73%`
        
    -   **Optimized Model Accuracy:**  `79%`
        
-   **Optimization Steps Taken:**
    
    -   Removed unnecessary columns (`STATUS`, `SPECIAL_CONSIDERATIONS`)
        
    -   Replaced infrequent categorical values with "Other" to reduce noise
        
    -   Increased the number of neurons in the first hidden layer
        
    -   Added a third hidden layer for deeper feature extraction
        
    -   Adjusted activation functions for improved learning
        
## 3. Summary

`AlphabetSoupCharity_Optimization.h5` successfully improved accuracy from **73% to 79%**, demonstrating a significant enhancement in predictive performance. However, further improvements could be achieved by:

-   **Testing Alternative Models:**
    
    -   A **Random Forest Classifier** may perform better with structured categorical data.

Overall, while deep learning provides a strong baseline, experimenting with tree-based ensemble models may yield even better results for this classification problem.
