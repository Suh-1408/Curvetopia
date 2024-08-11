
# Curvetopia

Curvetopia is a comprehensive project aimed at identifying, regularizing, and beautifying 2D curves. The project processes polylines to fit and smooth shapes like circles, ellipses, polygons, and Bézier curves, providing tools to handle isolated and fragmented curves, detect symmetry, and complete incomplete curves.

## Objective

The objective of Curvetopia is to:

1. **Regularize Curves**: Fit and simplify curves to regular shapes including straight lines, circles, ellipses, polygons, and Bézier curves.
2. **Detect Symmetry**: Identify symmetrical shapes and structures within the set of curves.
3. **Complete Incomplete Curves**: Use computer vision techniques to fill gaps in curves caused by occlusions or incomplete data.

## Problem Description

The project begins by working with polylines defined by sequences of points. The goal is to output curves as connected sequences of cubic Bézier curves. 

**For visualization,** we use SVG format for rendering and compare the results with the expected outputs.

## Features

- **Regularize Curves**: Fit shapes like circles, ellipses, polygons, and Bézier curves.
- **Detect Symmetry**: Analyze curves to find symmetrical structures.
- **Complete Incomplete Curves**: Use techniques to complete curves that have gaps.

## Usage

1. **Read Data**: Use the provided `read_csv` function to load polylines from CSV files.
2. **Regularize Paths**: Apply the `regularize_paths` function to fit and simplify the curves.
3. **Plot Results**: Visualize the results using the `plot` function to compare original, expected, and current output curves.

## Example

To use the project:

1. Load the input data from a CSV file:
   ```python
   paths_XYs = read_csv("path_to_input.csv")
   ```

2. Regularize the paths with a specified epsilon value:
   ```python
   fitted_paths = regularize_paths(paths_XYs, epsilon)
   ```

3. Plot the results:
   ```python
   plot(paths_XYs, 'Original Input', ax[0])
   plot(expected_output, 'Expected Output', ax[1])
   plot(fitted_paths, 'Current Output', ax[2])
   ```

## Code Overview

- `simplification.py`: Contains the Ramer-Douglas-Peucker algorithm for curve simplification.
- `fit_shapes.py`: Functions to fit circles, ellipses, polygons, Bézier curves, and detect star shapes.
- `icp.py`: Implements the Iterative Closest Point algorithm for merging curves.
- `plotting.py`: Functions for visualizing curves.
- `read_data.py`: Functions for reading CSV files containing polyline data.
