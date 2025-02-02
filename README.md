## Hi there 👋
Step 1: Import Libraries
First, import necessary libraries for data manipulation, plotting, and linear regression.

python
Copy code
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score
Step 2: Generate or Load Dataset
For demonstration purposes, let's generate a synthetic dataset with continuous features and a continuous target variable.

python
Copy code
# Generate synthetic dataset
np.random.seed(0)
X = 2 * np.random.rand(100, 1)    # Generate 100 random numbers between 0 and 2
y = 4 + 3 * X + np.random.randn(100, 1)   # y = 4 + 3*X + noise
Step 3: Split Data into Training and Testing Sets
Split the dataset into training and testing sets. This is typically done to train the model on one subset and evaluate it on another subset to assess its performance.

python
Copy code
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
Step 4: Train the Linear Regression Model
Instantiate the Linear Regression model and fit it to the training data.

python
Copy code
# Create a linear regression object
model = LinearRegression()

# Train the model using the training sets
model.fit(X_train, y_train)
Step 5: Evaluate the Model
Evaluate the model's performance using metrics such as Mean Squared Error (MSE) and R-squared on the test set.

python
Copy code
# Make predictions using the testing set
y_pred = model.predict(X_test)

# The coefficients
print('Coefficients:', model.coef_)
# The mean squared error
print('Mean Squared Error:', mean_squared_error(y_test, y_pred))
# The coefficient of determination: 1 is perfect prediction
print('R-squared:', r2_score(y_test, y_pred))
Step 6: Visualize the Results
Visualize the regression line and the actual vs. predicted values to assess the model's accuracy.

python
Copy code
# Plot outputs
plt.scatter(X_test, y_test,  color='black')
plt.plot(X_test, y_pred, color='blue', linewidth=3)

plt.title('Linear Regression')
plt.xlabel('X')
plt.ylabel('y')

plt.xticks(())
plt.yticks(())

plt.show()
Complete Code Example
Here's the complete code example putting it all together:

python
Copy code
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

# Generate synthetic dataset
np.random.seed(0)
X = 2 * np.random.rand(100, 1)    # Generate 100 random numbers between 0 and 2
y = 4 + 3 * X + np.random.randn(100, 1)   # y = 4 + 3*X + noise

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a linear regression object
model = LinearRegression()

# Train the model using the training sets
model.fit(X_train, y_train)

# Make predictions using the testing set
y_pred = model.predict(X_test)

# The coefficients
print('Coefficients:', model.coef_)
# The mean squared error
print('Mean Squared Error:', mean_squared_error(y_test, y_pred))
# The coefficient of determination: 1 is perfect prediction
print('R-squared:', r2_score(y_test, y_pred))

# Plot outputs
plt.scatter(X_test, y_test,  color='black')
plt.plot(X_test, y_pred, color='blue', linewidth=3)

plt.title('Linear Regression')
plt.xlabel('X')
plt.ylabel('y')

plt.xticks(())
plt.yticks(())

plt.show()
