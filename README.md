# Sales Data Analyzer

## Overview

**Sales Data Analyzer** is a menu-driven Python application developed to explore, clean, analyze, and visualize sales data stored in CSV files. It uses Pandas for data manipulation, Seaborn and Matplotlib for data visualization, and descriptive statistical methods to help users understand their datasets.

The project uses a sales dataset from Kaggle and provides practical experience with real-world data analysis workflows, including handling missing values, selecting and filtering records, generating statistical summaries, and creating different types of plots.

## Dataset

The project uses the following Kaggle dataset:

**Dataset Name:** Sales Dataset

**Source:** Kaggle

**Dataset Link:** https://www.kaggle.com/datasets/vinothkannaece/sales-dataset?resource=download

Download the dataset from Kaggle and extract the CSV file if it is provided in a compressed archive. When running the program, enter the path to the downloaded CSV file.

The program is designed to work with CSV datasets. The exact column names and data types depend on the downloaded dataset, so check the available columns before performing analysis or creating visualizations.

## Features

### 1. Load Dataset
- Import a CSV dataset using Pandas.
- Store the loaded data in a DataFrame.
- Handle common file-loading errors, including missing files and permission issues.
- Display a confirmation message after successfully loading the dataset.

### 2. Explore Data
Inspect the dataset through the following options:
- Display the first five rows using `head()`.
- Display the last five rows using `tail()`.
- Display all column names.
- Display the data type of each column.
- Display basic DataFrame information, including column types and non-null counts.

### 3. Perform DataFrame Operations
Perform common operations on the loaded dataset:
- **Select Specific Columns:** Display selected columns by entering their names separated by spaces.
- **Select Rows Range:** Display a range of rows using integer-based indexing.
- **Sort by Columns:** Sort data in ascending or descending order using a selected column.
- **Filter by Threshold:** Display rows where a selected column's value is greater than or equal to a specified numeric threshold.

### 4. Handle Missing Data
Identify and manage missing values in the dataset:
- **Display Rows with Missing Values:** Find and display rows containing null values.
- **Fill Missing Values with Mean:** Replace missing numeric values with the mean of their respective columns.
- **Drop Missing Values:** Remove rows containing missing values.
- **Replace Missing Values with a Specific Value:** Attempt to fill missing values in numeric or non-numeric columns using a user-provided value.

These operations modify the DataFrame in memory where applicable. The original CSV file is not automatically overwritten.

### 5. Generate Descriptive Statistics
Generate a statistical summary of the dataset using Pandas:

    self.data.describe(include="all").round(2)

The summary can include:
- Count of non-null values
- Mean and standard deviation
- Minimum and maximum values
- Quartiles
- Number of unique values in categorical columns
- Most frequent values and their frequencies, where applicable

Numeric results are rounded to two decimal places.

The program also allows users to save the descriptive statistics to a text file, such as `statistics.txt`. It uses exclusive file creation mode (`"x"`) to avoid overwriting an existing file with the same name.

### 6. Data Visualization
Create six types of visualizations using Seaborn and Matplotlib.

#### Bar Plot
Compare a selected category with a numerical value. For example, visualize sales by product if the corresponding columns exist in the dataset.

#### Line Plot
Visualize patterns or trends between two selected variables. This is useful for time-based data when the relevant columns are available.

#### Scatter Plot
Examine the relationship between two variables. For example, compare sales and profit if both columns are present.

#### Pie Chart
Display the frequency distribution of values in a selected column. The chart uses `value_counts()` to calculate category frequencies and adds percentage annotations.

#### Histogram
Visualize the distribution of values in a selected column. Users can specify the number of bins.

#### Stack Plot
Compare cumulative values across categories and groups. The program creates a pivot table that sums a selected numerical column for each combination of the chosen category and grouping column. At least two groups are required.

### 7. Save Visualization
Save the most recently generated plot as an image file.

- Enter an image filename, such as `sales.png`.
- The program saves the figure using Matplotlib's `savefig()`.
- The image is saved at 300 DPI with a tight bounding box.
- If no visualization is available, the program displays an error message.

### 8. Exit
Exit the application through the main menu.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | CSV loading, DataFrame operations, data cleaning, and statistical analysis |
| Seaborn | Creating statistical visualizations |
| Matplotlib | Displaying and saving plots |
| Kaggle | Source of the sales dataset |
| CSV | Dataset file format |

## Requirements

- Python 3.10 or later
- Pandas
- Matplotlib
- Seaborn
- A CSV dataset downloaded from Kaggle

Python 3.10 or later is required because the application uses `match-case` statements.

## Installation and Setup

### 1. Install Python

Install Python 3.10 or later if it is not already installed.

### 2. Download the Dataset

Visit the Kaggle dataset page:

https://www.kaggle.com/datasets/vinothkannaece/sales-dataset?resource=download

Download the dataset and extract the CSV file if necessary.

### 3. Install Required Libraries

Open a terminal or command prompt and run:

    pip install pandas matplotlib seaborn

### 4. Save the Python Program

Save the source code in a Python file, for example:

    sales_data_analyzer.py

### 5. Run the Program

Open a terminal in the directory containing the Python file and run:

    python sales_data_analyzer.py

## Main Menu

When the program starts, the following menu is displayed:

    ========== Data Analysis & Visualization Program ==========
    Please select an option:
    1. Load Dataset
    2. Explore Data
    3. Perform DataFrame Operations
    4. Handle Missing Data
    5. Generate Descriptive Statistics
    6. Data Visualization
    7. Save Visualization
    8. Exit

Enter the number corresponding to the operation you want to perform.

**Important:** Load the dataset before selecting an option that requires data.

## How to Use

### Step 1: Load the Dataset

Select option `1` and enter the path to the downloaded CSV file.

Example:

    Enter the path of the dataset (CSV file): sales.csv

The program loads the file into a Pandas DataFrame.

### Step 2: Explore the Data

Select option `2` to inspect the dataset.

You can view the first five rows, last five rows, column names, data types, and basic DataFrame information.

### Step 3: Perform DataFrame Operations

Select option `3` to access column selection, row selection, sorting, and threshold filtering.

For example, to sort by a column:

    Enter column name: Sales
    Ascending or Descending(a/d): a

Use a column name that actually exists in the downloaded dataset. The example above assumes that the dataset contains a column named `Sales`.

### Step 4: Handle Missing Data

Select option `4` to inspect or manage missing values.

For example, selecting the mean-filling option replaces missing numeric values with the corresponding column means. Dropping missing values removes incomplete rows from the in-memory DataFrame.

### Step 5: Generate Descriptive Statistics

Select option `5` to display a statistical summary of the loaded data.

The program then asks whether you want to save the summary to a text file.

Example:

    Save descriptive statistics as a file?(y/n): y
    Enter file name(e.g., statistics.txt): statistics.txt

If the filename already exists, the program reports an error rather than overwriting it.

### Step 6: Generate a Visualization

Select option `6` and choose one of the six available plots.

For example, a bar plot prompts you to enter the x-axis and y-axis column names. The program then displays the chart if the selected columns are suitable for the visualization.

The available plot types are:
1. Bar Plot
2. Line Plot
3. Scatter Plot
4. Pie Chart
5. Histogram
6. Stack Plot

### Step 7: Save the Visualization

After generating a plot, select option `7` and enter an image filename.

Example:

    Enter image name (e.g., sales.png): sales.png

The most recently captured plot is saved in the current working directory unless another path is provided.

### Step 8: Exit the Application

Select option `8` to exit the program.

## Class and Method Overview

The application uses the `SalesDataAnalyzer` class to organize its data analysis functionality.

| Method | Purpose |
|---|---|
| `__init__()` | Initializes the dataset attribute as `None`. |
| `load_data(file_path)` | Loads a CSV file into a DataFrame and handles selected file-loading errors. |
| `explore_data(option)` | Returns dataset previews, column names, data types, or basic information. |
| `clean_data(choice)` | Displays missing-value rows, fills missing numeric values, drops incomplete rows, or attempts specific-value replacement. |
| `methamatical_operations()` | Placeholder for mathematical operations; currently not implemented. |
| `combine_data()` | Placeholder for combining datasets; currently not implemented. |
| `split_data()` | Placeholder for splitting datasets; currently not implemented. |
| `search_sort_filter(choice)` | Selects columns or rows, sorts values, and filters rows by a numeric threshold. |
| `aggregate_functions()` | Placeholder; descriptive statistics are handled by another method. |
| `statistical_analysis()` | Generates descriptive statistics and rounds the results to two decimal places. |
| `create_pivot_table(x_axis, y_axis, group_column)` | Creates a pivot table that sums values for selected categories and groups. |
| `visualize_data(plot)` | Generates the selected visualization and stores the current Matplotlib figure for saving. |

## Important Functions and Methods

| Function or Method | Purpose |
|---|---|
| `pd.read_csv()` | Reads a CSV file into a DataFrame. |
| `pd.DataFrame()` | Creates a DataFrame. |
| `.head()` | Returns the first five rows by default. |
| `.tail()` | Returns the last five rows by default. |
| `.columns.tolist()` | Converts column names into a list. |
| `.dtypes` | Retrieves column data types. |
| `.info()` | Displays DataFrame structure and non-null counts. |
| `.isna()` | Identifies missing values. |
| `.select_dtypes()` | Selects columns according to their data types. |
| `.fillna()` | Fills missing values. |
| `.dropna()` | Removes rows or columns containing missing values, depending on its arguments. |
| `.sort_values()` | Sorts data using a selected column. |
| `.iloc[]` | Selects rows by integer position. |
| `.describe()` | Generates descriptive statistics. |
| `.pivot_table()` | Summarizes values across selected categories. |
| `.value_counts()` | Counts the occurrences of unique values. |
| `.to_string()` | Converts tabular output into text. |
| `sb.barplot()` | Creates a bar plot. |
| `sb.lineplot()` | Creates a line plot. |
| `sb.scatterplot()` | Creates a scatter plot. |
| `sb.histplot()` | Creates a histogram. |
| `plt.pie()` | Creates a pie chart. |
| `plt.stackplot()` | Creates a stacked area plot. |
| `plt.gcf()` | Retrieves the current Matplotlib figure. |
| `plt.show()` | Displays a plot. |
| `savefig()` | Saves a figure to an image file. |

## Project Structure

    Sales-Data-Analyzer/
    ├── sales_data_analyzer.py
    ├── sales.csv
    ├── statistics.txt
    └── README.md

- `sales_data_analyzer.py`: Main Python program.
- `sales.csv`: Downloaded Kaggle dataset, or another compatible CSV file.
- `statistics.txt`: Optional output file created when descriptive statistics are saved.
- `README.md`: Project documentation.

The CSV and text files shown above are examples. The statistics file is created only when the user chooses to save the output.

## Notes and Limitations

- The program is designed to work with CSV files.
- Column names must match the actual dataset. Some operations convert entered names using `.title()`, which may not work for every capitalization style or column name.
- The threshold filter expects an integer threshold and a compatible numerical column.
- The row-selection operation uses `iloc`, whose ending position is exclusive.
- Filling missing values with the mean applies to numeric columns. Non-numeric missing values may remain.
- The specific-value replacement option currently recognizes only inputs classified by `isnumeric()` or `isalpha()`. Decimal numbers, negative numbers, and mixed alphanumeric strings may not be handled as intended.
- Some plots require suitable column data types. For example, scatter plots generally require numeric columns, and histograms are most useful for numerical data.
- The stack plot requires at least two distinct groups.
- Changes made during cleaning are held in memory and are not automatically written back to the original CSV file.
- The mathematical operations, dataset combination, dataset splitting, and separate aggregate-functions methods are placeholders.
- The application handles selected errors, but some invalid inputs or incompatible datasets may still cause errors.

## Future Improvements

Potential enhancements include:
- Adding more robust validation for column names and user inputs.
- Supporting decimal and negative numeric thresholds.
- Improving the handling of categorical and numerical missing values.
- Adding an option to export cleaned data to a new CSV file.
- Implementing mathematical operations and dataset combination/splitting.
- Adding more visualization options, such as box plots and heatmaps.
- Improving plot formatting and saving options.
- Adding automated tests for data loading, cleaning, filtering, and visualization.

## Learning Objectives

This project provides practical experience with:
- Python classes and object-oriented programming
- Menu-driven applications using loops and `match-case`
- Exception handling
- CSV file handling
- Pandas DataFrame operations
- Missing-value detection and cleaning
- Sorting and filtering datasets
- Descriptive statistical analysis
- Pivot tables and grouped data
- Data visualization using Seaborn and Matplotlib
- Saving statistical reports and visualization images

## Conclusion

Sales Data Analyzer is a practical Python project for working with sales datasets obtained from Kaggle. It combines dataset exploration, data cleaning, DataFrame operations, descriptive statistics, and multiple visualization techniques in a single menu-driven application.

The project provides a foundation for understanding data analysis with Pandas and creating meaningful visualizations with Seaborn and Matplotlib.
