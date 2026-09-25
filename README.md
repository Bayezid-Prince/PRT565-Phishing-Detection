\# Explainable and Cost-Sensitive Phishing Website Detection



This project was developed for \*\*PRT565 – Machine Learning and Artificial Intelligence\*\* at Charles Darwin University.



The project investigates phishing website detection using conventional machine learning and a multilayer artificial neural network, with additional experiments on \*\*cost-sensitive learning\*\* and \*\*SHAP-based explainability\*\*.



\## Project Objectives



The main objectives are to:



\- Compare multiple machine learning and deep learning approaches for phishing website detection.

\- Evaluate models using Accuracy, Precision, Recall, F1-score, ROC-AUC, and confusion matrices.

\- Investigate whether assigning a higher cost to phishing misclassification can reduce dangerous phishing false negatives.

\- Use SHAP to identify the website characteristics that most strongly influence model predictions.



\## Dataset



The project uses the \*\*PhiUSIIL Phishing URL (Website) Dataset\*\* from the UCI Machine Learning Repository.



The original dataset contains \*\*235,795 website instances\*\*, including legitimate and phishing websites.



For modelling, raw textual/identifier fields such as `FILENAME`, `URL`, `Domain`, `TLD`, and `Title` were excluded. The resulting modelling dataset contains \*\*50 predictor features\*\* and the target label.



The data was divided using a stratified train/validation/test split.



\- Training: 70%

\- Validation: 15%

\- Testing: 15%

\- Random state: 42



The source dataset uses:



\- `0` = Phishing

\- `1` = Legitimate



\## Models



Four classification models were evaluated:



1\. Decision Tree

2\. Random Forest

3\. Gaussian Naive Bayes

4\. Multilayer Artificial Neural Network (ANN)



\## Cost-Sensitive Learning



To investigate the impact of phishing misclassification costs, experiments were performed using phishing class weights:



`1, 2, 5, 10`



The analysis focuses particularly on phishing false negatives, representing phishing websites incorrectly classified as legitimate.



\## Explainable AI



SHAP (SHapley Additive exPlanations) was used to explain the behaviour of the Random Forest model.



The most influential feature was:



`URLSimilarityIndex`



Other important features included:



\- `NoOfSelfRef`

\- `NoOfExternalRef`

\- `LineOfCode`

\- `NoOfImage`

\- `HasSocialNet`

\- `NoOfJS`

\- `IsHTTPS`



The SHAP results are available in the `results\_xai` directory.



\## Repository Structure



```text

PRT565-Phishing-Detection/

│

├── 01\_Baseline\_Models.ipynb

├── 02\_Cost\_Sensitive\_Models.ipynb

├── 03\_SHAP\_Explainability.ipynb

├── requirements.txt

│

├── results\_baseline/

│   ├── baseline\_model\_results.csv

│   └── confusion matrix figures

│

├── results\_cost\_sensitive/

│   └── cost\_sensitive\_results.csv

│

└── results\_xai/

&#x20;   ├── shap\_feature\_importance.csv

&#x20;   ├── shap\_beeswarm.png

&#x20;   └── shap\_global\_bar.png

