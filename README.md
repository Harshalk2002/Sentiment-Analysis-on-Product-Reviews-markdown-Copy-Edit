# 📚 Sentiment Analysis on Product Reviews
**Homework 4 - Machine Learning Project**

## 🚀 Project Overview
This project focuses on performing **sentiment analysis** on product reviews from a provided dataset. The goal is to predict whether a review expresses **positive** or **negative** sentiment based solely on its textual content. These predictions are compared against actual product ratings to evaluate the accuracy and performance of the models.

---

## 🗃️ Dataset Description
**File**: `product_reviews_with_sentiment.csv`  
- **Total Records**: 34,627  
- **Features**:
  - `product_id`: Product identifier (not used in analysis)
  - `product_rating`: Customer rating (1 to 5 scale)
  - `product_review`: Customer review text (used for sentiment prediction)
  - `Unnamed: 0`: Index column (removed during preprocessing)

---

## 📝 Preprocessing Steps
1. **Removed unnecessary columns** (`Unnamed: 0`, `product_id`).
2. **Filtered out neutral reviews** (ratings of 3).
3. **Mapped ratings**:
   - Ratings 4 and 5 → **Positive (1)**
   - Ratings 1 and 2 → **Negative (0)**
4. Addressed **class imbalance** using **SMOTE (Synthetic Minority Over-sampling Technique)**.

---

## 🛠️ Methodology
### 1. **Text Vectorization**
- **TF-IDF** (Term Frequency-Inverse Document Frequency)
- Max Features: 5000  
- Stop Words: English  

### 2. **Handling Class Imbalance**
- **SMOTE** applied on the training dataset to balance the number of positive and negative samples.

### 3. **Classification Models**
Three models were trained and evaluated:
- **Logistic Regression (SMOTE)**
- **Random Forest Classifier (SMOTE)**
- **XGBoost Classifier (SMOTE)**

---

## 📊 Results & Evaluation
| Model                | Accuracy | Recall (Negative Class) | Precision (Negative Class) | F1-Score (Negative Class) |
|----------------------|----------|-------------------------|----------------------------|---------------------------|
| Logistic Regression  | 92.76%   | **69%**                | 22%                       | 33%                      |
| Random Forest        | **97.34%** | 18%                  | **48%**                   | 27%                      |
| XGBoost              | 95.65%   | 48%                    | 30%                       | **37%**                  |

➡️ **Final Model Selected**: **XGBoost (SMOTE)**  
**Reason**: Balanced trade-off between precision and recall for the negative class. XGBoost outperforms Random Forest in recall and offers better precision than Logistic Regression.

---


