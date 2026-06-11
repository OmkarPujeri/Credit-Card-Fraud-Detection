## Class Distribution
![Class Distribution](<img width="590" height="390" alt="download" src="https://github.com/user-attachments/assets/236e78ec-33f1-40b8-a2fd-01627e6eec04" />)


The dataset has 284,315 legit transactions and only 492 fraud cases (0.17%).
A dummy classifier predicting "legit" every time scores 99.8% accuracy —
which is why ROC-AUC and Recall are used as primary metrics instead.

## Transaction Amount Analysis
![Amount Distribution](<img width="1390" height="390" alt="download (1)" src="https://github.com/user-attachments/assets/31399e3a-50e3-4516-81d2-687c4dc1b78d" />
)

Fraudulent transactions tend to be smaller amounts, mostly under $500,
while legit transactions span a much wider range up to $25,000.

## Feature Correlation with Fraud
![Feature Correlation](<img width="790" height="590" alt="download (2)" src="https://github.com/user-attachments/assets/abca9bb5-d1b7-41b1-9e9e-4ba6ff7e2ad8" />
)

V17 and V14 show the strongest negative correlation with fraud,
while V11 and V4 show positive correlation.

## Results

| Model               | ROC-AUC | Fraud Recall | Fraud Precision |
|---------------------|---------|--------------|-----------------|
| Logistic Regression | 0.9698  | 92%          | 6%              |
| Random Forest       | 0.9688  | 81%          | 81%             |
| XGBoost             | **0.9792**  | **89%**  | 73%             |

## ROC Curves
![ROC Curves](<img width="1770" height="495" alt="download (3)" src="https://github.com/user-attachments/assets/ff2dac66-de1c-4b15-80d4-22b4b5ce6c4e" />
)

## Confusion Matrices
![Confusion Matrices](<img width="790" height="590" alt="download (4)" src="https://github.com/user-attachments/assets/8d900a29-653f-4ee2-a76a-4333407532a7" />
)

XGBoost flagged only 32 false positives vs Logistic Regression's 1,458 —
a critical difference for real-world deployment where operations teams
investigate every flagged transaction.

## Feature Importances
![Feature Importances](<img width="989" height="590" alt="download (5)" src="https://github.com/user-attachments/assets/d29113c5-1e04-4a74-9c91-a7e972fd2132" />
)

V14 dominates with an importance score of ~0.59, nearly 10x the next
feature (V4). This suggests fraud patterns are heavily concentrated
in a single PCA component.
