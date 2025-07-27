# 🎓 Academic Course Recommender System Using Machine Learning

> A personalized recommender system for Master's students in Information Technology and Business Analytics, designed to suggest the most suitable courses based on academic profiles, interests, and career goals.

## Project Overview

This project addresses the challenge faced by Master's students in selecting courses aligned with their goals. Built in two phases — binary classification and content-based recommendation — the system predicts course suitability across five courses and delivers ranked, interpretable recommendations based on a student's profile.

---

## Problem Statement

Many graduate students struggle with course selection due to lack of structured guidance. This project aims to:
- Predict if a course is suitable for a student using binary classification.
- Recommend top-fit courses based on predicted suitability and CareerTrack alignment.

---

## Dataset

- **Source**: Custom survey via Google Forms
- **Total records**: 55
- **Features collected**:
  - Career Track (e.g., Data Science/AI, Cybersecurity)
  - Preferred Learning Style
  - Study Hours
  - Interest Levels per course (1–5)
  - Reason for choosing the course
  - Semester
  - Course Suitability (target: Yes/No for each course)

[📄 Google Form Link](https://forms.gle/KJZQhPz8pjdHrWL56)

---

## Methodology

### 🔹 Phase 1: Binary Classification

- **Goal**: Predict course suitability (Yes/No)
- **Models used**:  
  - ✅ Logistic Regression *(F1 = 0.900)*  
  - Random Forest  
  - Decision Tree  
  - Logistic Regression with Polynomial Features  
  - Logistic Regression with PCA-based feature reduction

- **Techniques**:
  - Class imbalance handling with `class_weight=balanced`
  - OneHotEncoding for categorical variables
  - Imputation using mean/mode
  - K-Fold Cross-Validation
  - Learning curve analysis for overfitting detection

### 🔹 Phase 2: Content-Based Recommendation

- **Goal**: Recommend courses based on CareerTrack and predicted suitability
- **Approach**:
  - Rank courses by suitability probability from Phase 1
  - Boost probabilities if student's track matches course's ideal profile
  - Penalize over-represented courses (e.g., ADML)
  - Visualize career track alignment per course

---

## A/B Hypothesis Testing

- **Goal**: Validate whether probability-adjusted ranking improves recommendation quality
- **Method**: 
  - Group A received baseline suitability ranking  
  - Group B received adjusted probability ranking  
  - Conducted Chi-square tests (p < 0.05) showing statistically significant improvement in alignment with career aspirations in Group B

---

## Key Results

- **Best Model**: Logistic Regression
  - F1-score: **0.900**
  - Precision: 0.818
  - Recall: 1.000

- **Top Recommendation Example** (CareerTrack: Data Science / AI):
  - PCM (Suitability: 0.809)
  - BI (Suitability: 0.796)
  - BDCN (Suitability: 0.750)

- **Visualization**:
  - Course-to-career alignment heatmaps
  - Top-5 course distributions based on learning style and career goals

---

## Technologies Used

| Tool/Library       | Usage                                 |
|--------------------|----------------------------------------|
| `Python`           | Core programming language              |
| `Scikit-learn`     | Classification models, TF-IDF, tuning  |
| `Pandas`/`NumPy`   | Data manipulation and preprocessing    |
| `Matplotlib`/`Seaborn` | Visualization of results             |
| `Google Forms`     | Data collection                        |
| `Chi-Square Test`  | Hypothesis testing for A/B validation  |
| `PolynomialFeatures`, `PCA` | Feature engineering/reduction  |

---

## Future Improvements

- Expand dataset size (current = 55)
- Add collaborative filtering module for hybrid recommendation
- Develop an interactive UI using Flask/Streamlit
- Integrate student feedback loop for ongoing refinement
- Perform feature selection using Recursive Feature Elimination (RFE)

---

## Author

**Pavitra Aritas Raghunath Sharma**  
Graduate Student, MSIT  
[LinkedIn](https://linkedin.com/in/pavitra-aritas)

---

## License

This project is for academic use. Contact the author for reuse permissions.
