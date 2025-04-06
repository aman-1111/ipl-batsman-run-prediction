# 🏏 IPL Batsman Run Prediction using Machine Learning

This project uses machine learning to predict the number of runs a batsman scores on each delivery in IPL matches (2008–2022). The goal is to build a regression model that learns from contextual features like bowler, batsman, venue, and match situation.

## 📊 Dataset

- **Source**: IPL Ball-by-Ball Dataset (2008–2022)
- **Rows**: 1.5M+ deliveries
- **Key Columns**:
  - `batsman_run`: Target variable (runs scored on the ball)
  - `batsman`, `bowler`, `venue`, `match_id`, etc.
  - **Excluded**: `total_run`, `extras_run` to avoid data leakage

## 📌 Problem Statement

> Predict the number of runs scored (`batsman_run`) on a single ball using contextual match features.

## 🔍 Data Preprocessing

- Removed columns that directly leak the target (`total_run`, `extras_run`)
- Encoded categorical columns using `LabelEncoder`
- Handled missing values with `.dropna()`
- Split into training and test sets (80/20)

## 🧠 Model Used

- `RandomForestRegressor` from Scikit-learn
- Evaluation Metrics:
  - **MSE** (Mean Squared Error)
  - **RMSE** (Root Mean Squared Error)

## 📈 Results

| Metric | Value |
|--------|--------|
| MSE    | 2.76   |
| RMSE   | 1.66   |

The model performs reasonably well considering the unpredictability of T20 cricket. Further improvements can be done using advanced features or deep learning models.

## 🧠 Lessons Learned

- Importance of checking for **data leakage** before training
- `total_run` was derived from the target (`batsman_run + extras_run`), which caused unrealistically perfect predictions (MSE = 0) before fixing
- Always validate features against the target to avoid overfitting

## 🚀 Future Work

- Try advanced models like XGBoost or LightGBM
- Use OneHotEncoding for teams/venues
- Create a classification version (e.g., "Will the batsman hit a 4 or 6?")
- Build an interactive dashboard with predictions

## 📂 Project Structure


## ✍️ Author

- **Aman Chaurasia** – [LinkedIn](https://www.linkedin.com/in/amanchaurasia07/) | [GitHub](https://github.com/aman-1111)

---

Feel free to fork or star ⭐ this repo if you find it useful!
