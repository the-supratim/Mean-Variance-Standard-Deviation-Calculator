# Mean-Variance-Standard Deviation Calculator

This is the boilerplate for the Mean-Variance-Standard Deviation Calculator project. Instructions for building your project can be found at https://www.freecodecamp.org/learn/data-analysis-with-python/data-analysis-with-python-projects/mean-variance-standard-deviation-calculator

### Project Description

Create a function named `calculate()` that uses a list of 9 numbers as input. The function should convert the list into a 3x3 NumPy array, then return a dictionary containing the mean, variance, standard deviation, maximum, minimum, and sum of the array elements. The calculations should be done for the rows, columns, and the entire array.

### Function Specifications

1. **Input**: A list of 9 numbers.
2. **Output**: A dictionary with the mean, variance, standard deviation, maximum, minimum, and sum for the rows, columns, and the entire array.

### Steps to Follow

1. **Input Validation**:
   - Ensure the list contains exactly 9 numbers.
   - Raise a `ValueError` if the input list does not contain 9 elements.

2. **Conversion to 3x3 NumPy Array**:
   - Convert the list into a 3x3 NumPy array.

3. **Calculations**:
   - Calculate the mean, variance, standard deviation, maximum, minimum, and sum for each row, each column, and the entire array.
   - Use NumPy functions like `numpy.mean()`, `numpy.var()`, `numpy.std()`, `numpy.max()`, `numpy.min()`, and `numpy.sum()` for these calculations.

4. **Output**:
   - Return the results in a dictionary with the following structure:
     ```python
     {
       'mean': [axis1_mean, axis2_mean, flattened_mean],
       'variance': [axis1_variance, axis2_variance, flattened_variance],
       'standard deviation': [axis1_std, axis2_std, flattened_std],
       'max': [axis1_max, axis2_max, flattened_max],
       'min': [axis1_min, axis2_min, flattened_min],
       'sum': [axis1_sum, axis2_sum, flattened_sum]
     }
     ```
   - Each list in the dictionary should contain three lists: one for rows, one for columns, and one for the entire array.

### Example

```python
import numpy as np

def calculate(list):
    if len(list) != 9:
        raise ValueError("List must contain nine numbers.")
    
    array = np.array(list).reshape(3, 3)
    
    calculations = {
        'mean': [
            np.mean(array, axis=0).tolist(),
            np.mean(array, axis=1).tolist(),
            np.mean(array).tolist()
        ],
        'variance': [
            np.var(array, axis=0).tolist(),
            np.var(array, axis=1).tolist(),
            np.var(array).tolist()
        ],
        'standard deviation': [
            np.std(array, axis=0).tolist(),
            np.std(array, axis=1).tolist(),
            np.std(array).tolist()
        ],
        'max': [
            np.max(array, axis=0).tolist(),
            np.max(array, axis=1).tolist(),
            np.max(array).tolist()
        ],
        'min': [
            np.min(array, axis=0).tolist(),
            np.min(array, axis=1).tolist(),
            np.min(array).tolist()
        ],
        'sum': [
            np.sum(array, axis=0).tolist(),
            np.sum(array, axis=1).tolist(),
            np.sum(array).tolist()
        ]
    }
    
    return calculations

# Example usage:
input_list = [0, 1, 2, 3, 4, 5, 6, 7, 8]
print(calculate(input_list))
```

### Expected Output

For the input list `[0, 1, 2, 3, 4, 5, 6, 7, 8]`, the expected output is:
```python
{
  'mean': [
    [3.0, 4.0, 5.0],  # Mean of columns
    [1.0, 4.0, 7.0],  # Mean of rows
    4.0               # Mean of the entire array
  ],
  'variance': [
    [6.0, 6.0, 6.0],  # Variance of columns
    [0.6666666666666666, 0.6666666666666666, 0.6666666666666666],  # Variance of rows
    6.666666666666667  # Variance of the entire array
  ],
  'standard deviation': [
    [2.449489742783178, 2.449489742783178, 2.449489742783178],  # Std of columns
    [0.816496580927726, 0.816496580927726, 0.816496580927726],  # Std of rows
    2.581988897471611   # Std of the entire array
  ],
  'max': [
    [6, 7, 8],  # Max of columns
    [2, 5, 8],  # Max of rows
    8           # Max of the entire array
  ],
  'min': [
    [0, 1, 2],  # Min of columns
    [0, 3, 6],  # Min of rows
    0           # Min of the entire array
  ],
  'sum': [
    [9, 12, 15],  # Sum of columns
    [3, 12, 21],  # Sum of rows
    36            # Sum of the entire array
  ]
}
```

This project provides practice with data manipulation and statistical calculations using NumPy, as well as experience with handling and validating function inputs.
