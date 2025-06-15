🚗 Car Price Predictor

This project builds a machine learning model to predict the **price of a car** based on several features such as year, fuel type, kilometers driven, number of previous owners, etc. It includes data preprocessing, model training, evaluation, and a simple prediction interface.

📁 Project Structure

```
Car_Price_predictor/
├── Car_Price_predictor.ipynb
├── README.md
└── dataset.csv (assumed from the notebook)
```

🔧 Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib / Seaborn
* Jupyter Notebook

📊 Features Used

* `Year` – Manufacturing year of the car
* `Present_Price` – Price of the car when new
* `Kms_Driven` – Total kilometers driven
* `Fuel_Type` – Petrol / Diesel / CNG
* `Seller_Type` – Dealer or Individual
* `Transmission` – Manual or Automatic
* `Owner` – Number of previous owners

🔄 Workflow

1. **Data Loading & Cleaning**

   * Null values checked and handled
   * Feature engineering to derive the car age (`Current_Year - Year`)
   * Irrelevant columns dropped

2. **EDA (Exploratory Data Analysis)**

   * Visualizations using heatmaps and bar charts
   * Feature importance checked using `ExtraTreesRegressor`

3. **Modeling**

   * Data split into training and test sets
   * Random Forest Regressor used
   * Hyperparameter tuning with `RandomizedSearchCV`

4. **Evaluation**

   * R² score and other metrics used to evaluate the model
   * Model predictions compared to actual values

5. **Model Persistence**

   * Model saved using `pickle` for reuse in deployment

📈 Performance Metrics

* **R² Score** and other regression metrics (as plotted)
* Good fit between predicted and actual prices

▶️ How to Run

1. Clone the repository or download the notebook.

2. Make sure you have Python and required libraries installed:

   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn jupyter
   ```

3. Launch the notebook:

   ```bash
   jupyter notebook Car_Price_predictor.ipynb
   ```

4. Follow the steps in the notebook to understand and run the prediction pipeline.

💾 Saved Model

The final trained model is saved as:

```python
pickle.dump(model, open('random_forest_regression_model.pkl', 'wb'))
```

This file can be loaded for future predictions using:

```python
model = pickle.load(open('random_forest_regression_model.pkl', 'rb'))
```

