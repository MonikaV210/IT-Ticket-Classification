# Intelligent IT Ticket Classification Module

## Project Overview
This module is part of an Intelligent IT Ticket Analysis and Resolution Assistant developed for the HCLTech AI Engineer Hackathon.

It automatically classifies employee IT complaints into categories and subcategories using Machine Learning.

## Technologies Used
- Python
- Pandas
- Scikit-learn
- TF-IDF Vectorizer
- Logistic Regression
- Joblib

## Dataset
- 1,800 IT support tickets
- 5 main categories
- 18 subcategories
- 100 examples per subcategory

## Architecture
1. Employee enters an IT complaint.
2. TF-IDF converts the complaint into numerical features.
3. Logistic Regression predicts the category and subcategory.
4. The system estimates confidence scores.
5. Rule-based logic estimates ticket priority.
6. Low-confidence predictions are flagged for human review.

## Model Performance
- Category Accuracy: 97.5%
- Subcategory Accuracy: 95%
- Category F1 Score: 0.974
- Subcategory F1 Score: 0.949

These results were measured on the held-out dataset. Performance on new complaints may differ.

## Installation

```bash
pip install -r requirements.txt
```

## Run Classification

```bash
python prediction.py
```

Enter an IT complaint when prompted.

## Frontend Integration

```python
from prediction import classify_ticket

result = classify_ticket("My office VPN is not connecting")
print(result)
```

The function returns the predicted category, subcategory, confidence scores, priority and human-review flag.

## Project Files
- `classifier.py` — Model training and evaluation
- `prediction.py` — Classification API for integration
- `category_model.pkl` — Trained category classifier
- `subcategory_model.pkl` — Trained subcategory classifier
- `Dataset_ticket.xlsx` — Classification dataset
- `test_model.py` — Manual testing
- `requirements.txt` — Python dependencies

## Limitations
The priority estimator uses simple rules. Confidence thresholds are provisional, and uncertain predictions require human review. The module does not automatically resolve or close IT tickets.
