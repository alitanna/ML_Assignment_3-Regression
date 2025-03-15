# ML_Assignment_3-Regression
1. Loading and Preprocessing

How do you load the California Housing dataset using the fetch_california_housing function from sklearn?

We load the California Housing dataset using the fetch_california_housing() function from the sklearn.datasets module. This function retrieves the dataset, which includes features such as house age, average rooms, population, and median house value.

How do you convert the dataset into a pandas DataFrame?

The dataset is converted into a pandas DataFrame using pd.DataFrame(). We pass the feature data and column names to make handling the dataset easier. The target variable (median house price) is added as a new column.

How do you handle missing values (if any) and perform necessary feature scaling (e.g., standardization)?

Missing Values: After inspecting the dataset using isnull().sum(), no missing values were found, so no imputation was necessary.

Feature Scaling: We applied standardization using StandardScaler() from sklearn.preprocessing to normalize the feature values. This ensures all features are on the same scale, which is crucial for algorithms sensitive to feature magnitudes (e.g., SVR).

What preprocessing steps did you perform, and why are they necessary for this dataset?

Checked for missing values: Ensures the dataset is clean and no data points are missing.

Feature Scaling: Standardized the features to improve convergence and performance, especially for models that rely on distance calculations (e.g., SVR).

Train-Test Split: Split the dataset into training (70%) and testing (30%) sets to evaluate model performance effectively.

2. Regression Algorithm Implementation

How does each regression algorithm work, and why might it be suitable for this dataset?

1. Linear Regression

How it Works: Fits a linear relationship between the input features and the target variable by minimizing the sum of squared residuals.

Suitability: Simple and interpretable. Useful as a baseline model to understand linear trends in the dataset.

2. Decision Tree Regressor

How it Works: Splits the dataset into branches based on feature values, minimizing variance within each branch.

Suitability: Captures non-linear relationships and interactions between features. Works well if the dataset has complex patterns.

3. Random Forest Regressor

How it Works: An ensemble of decision trees where each tree is trained on a random subset of data and features. Outputs the average prediction.

Suitability: Reduces overfitting compared to a single decision tree and handles large datasets effectively.

4. Gradient Boosting Regressor

How it Works: Builds decision trees sequentially, correcting the previous model’s errors using gradient descent.

Suitability: Provides high accuracy and handles complex patterns, although it is computationally intensive.

5. Support Vector Regressor (SVR)

How it Works: Finds a hyperplane that fits the data with a margin of tolerance (epsilon) around it to capture the target values.

Suitability: Effective for high-dimensional datasets and handles both linear and non-linear relationships.

3. Model Evaluation and Comparison

How do you evaluate the performance of each algorithm?

We evaluate performance using three key metrics:

Mean Squared Error (MSE): Measures the average squared difference between actual and predicted values. Lower MSE indicates better performance.

Mean Absolute Error (MAE): Measures the average absolute difference between actual and predicted values. Provides interpretability in the original units.

R-squared (R²): Represents the proportion of variance explained by the model. Higher R² indicates better model fit.

Which algorithm performed the best, and why?

The best-performing model is the Gradient Boosting Regressor, as it had the lowest MSE and MAE along with the highest R² score. This model’s sequential boosting strategy effectively captures complex relationships and minimizes errors.

Which algorithm performed the worst, and why?

The Linear Regression model performed the worst. It assumes a linear relationship between features and the target, which may not hold true for this dataset, resulting in higher errors and lower R².
