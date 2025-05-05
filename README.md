# Mean-Variance-Standard Deviation Calculator

This is the boilerplate for the Mean-Variance-Standard Deviation Calculator project. Instructions for building your project can be found at https://www.freecodecamp.org/learn/data-analysis-with-python/data-analysis-with-python-projects/mean-variance-standard-deviation-calculator
'mean': [axis1, axis2, flattened],
  'variance': [axis1, axis2, flattened],
  'standard deviation': [axis1, axis2, flattened],
  'max': [axis1, axis2, flattened],
  'min': [axis1, axis2, flattened],
  'sum': [axis1, axis2, flattened]
  mean_var_std.py
  import numpy as np

def calculate(input_list):
    # Ensure the list has exactly 9 elements
    if len(input_list) != 9:
        raise ValueError("List must contain nine numbers.")

    # Convert list to 3x3 numpy array
    matrix = np.array(input_list).reshape(3, 3)

    # Prepare the result dictionary
    calculations = {
        'mean': [
            matrix.mean(axis=0).tolist(),    # Mean of columns
            matrix.mean(axis=1).tolist(),    # Mean of rows
            matrix.mean().item()             # Mean of entire matrix
        ],
        'variance': [
            matrix.var(axis=0).tolist(),
            matrix.var(axis=1).tolist(),
            matrix.var().item()
        ],
        'standard deviation': [
            matrix.std(axis=0).tolist(),
            matrix.std(axis=1).tolist(),
            matrix.std().item()
        ],
        'max': [
            matrix.max(axis=0).tolist(),
            matrix.max(axis=1).tolist(),
            matrix.max().item()
        ],
        'min': [
            matrix.min(axis=0).tolist(),
            matrix.min(axis=1).tolist(),
            matrix.min().item()
        ],
        'sum': [
            matrix.sum(axis=0).tolist(),
            matrix.sum(axis=1).tolist(),
            matrix.sum().item()
        ]
    }
