#Basic data analysis
# Post-COVID Conditions Data Analysis

A basic Python data analysis tool providing statistical analysis and publication-quality visualizations for the Post-COVID Conditions dataset.

## Features

- Automated data loading with comprehensive error handling
- Missing value detection and intelligent cleaning strategies
- Statistical analysis with descriptive statistics and group comparisons
- Four professional, publication-quality visualizations
- Detailed summary reports with key insights

## Visualizations

The script generates four high-quality PNG files:

1. **1_temporal_trend_analysis.png** - Temporal progression with moving average overlay
2. **2_categorical_comparison_analysis.png** - Ranked categorical comparison with sample sizes
3. **3_distribution_analysis.png** - Distribution histogram with KDE overlay and statistical markers
4. **4_correlation_analysis.png** - Scatter plot with density coloring and regression analysis

All visualizations are saved at 300 DPI for publication quality.

## Requirements

- Python 3.6 or higher
- pandas
- numpy
- matplotlib
- seaborn
- scipy

## Installation and Setup

### Step 1: Download the Script

Download `covid_data_analysis.py` and place it in your project directory.

### Step 2: Prepare Your Data

Ensure your CSV file is named `Post-COVID_Conditions.csv` and placed in the same directory as the script.

### Step 3: Create Virtual Environment

Navigate to your project directory:
```bash
cd path/to/your/project
```

Create the virtual environment:
```bash
python3 -m venv venv
```

### Step 4: Activate Virtual Environment

On Linux/macOS:
```bash
source venv/bin/activate
```

On Windows Command Prompt:
```bash
venv\Scripts\activate
```

On Windows PowerShell:
```bash
venv\Scripts\Activate.ps1
```

### Step 5: Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scipy
```

Optional - save dependencies to file:
```bash
pip freeze > requirements.txt
```

### Step 6: Run the Analysis

```bash
python3 covid_data_analysis.py
```

## Project Structure

```
project/
├── venv/                          # Virtual environment (created by you)
├── covid_data_analysis.py         # Main analysis script
├── Post-COVID_Conditions.csv      # Your dataset
├── requirements.txt               # Python dependencies (optional)
├── README.md                      # This file
└── Output files (generated):
    ├── 1_temporal_trend_analysis.png
    ├── 2_categorical_comparison_analysis.png
    ├── 3_distribution_analysis.png
    └── 4_correlation_analysis.png
```

## What the Script Does

### Task 1: Data Loading and Exploration
- Loads CSV with error handling for missing or corrupt files
- Displays first 5 rows with formatted output
- Shows complete dataset information including shape and column types
- Analyzes missing values with counts and percentages
- Cleans data using median for numerical columns and mode for categorical columns

### Task 2: Statistical Analysis
- Computes comprehensive descriptive statistics for all numerical columns
- Performs group-based analysis on categorical variables
- Identifies key patterns including highest and lowest performing categories
- Displays statistical summaries with mean, count, and standard deviation

### Task 3: Professional Visualizations

**Temporal Trend Analysis**
- Line plot with gradient fill
- Moving average overlay for trend identification
- Clean, modern styling with minimal borders

**Categorical Comparison Analysis**
- Horizontal bar chart with gradient colors
- Ranked by average values
- Sample sizes displayed for each category
- Filters categories with insufficient data

**Distribution Analysis**
- Histogram with 40 bins for detailed distribution
- Kernel Density Estimation (KDE) overlay
- Mean and median markers with values
- Statistics box with key metrics

**Correlation Analysis**
- Density-colored scatter plot
- Regression line with visual fit
- Correlation coefficient and R² value
- Interpretation (Strong/Moderate/Weak correlation)

## Output

The script produces:
- Console output with detailed analysis results organized by task
- Four high-resolution PNG files (300 DPI) suitable for reports and presentations
- Statistical summaries with key findings
- Summary report with dataset overview and insights

## Customization

### Change Dataset File

Modify the filepath in the `main()` function:
```python
filepath = "your_dataset_name.csv"
```

### Adjust Visualization Size

Modify figure size in individual visualization sections:
```python
fig, ax = plt.subplots(figsize=(14, 7))  # Width, Height in inches
```

### Change Color Scheme

Edit the colors dictionary in `visualize_data()` function:
```python
colors = {
    'primary': '#2E86AB',    # Main color
    'secondary': '#A23B72',  # Secondary color
    'accent': '#F18F01',     # Accent color
    'success': '#06A77D',    # Success/positive
    'danger': '#D00000',     # Danger/negative
    'neutral': '#6C757D'     # Neutral
}
```

## Error Handling

The script handles multiple error scenarios:

**File not found** - Checks if CSV exists before loading

**Empty or corrupt CSV** - Catches parsing and empty data errors

**Missing values** - Automatically fills with appropriate strategies

**Insufficient data** - Skips visualizations that require minimum data points

**Type mismatches** - Separates numerical and categorical columns automatically

## Troubleshooting

**ModuleNotFoundError: No module named 'X'**

Ensure virtual environment is activated and all dependencies are installed:
```bash
pip install pandas numpy matplotlib seaborn scipy
```

**File not found error**

Verify the CSV file is in the same directory as the script or provide full path.

**Visualizations not generating**

Check that you have sufficient data in numerical and categorical columns. The script requires at least one numerical column for most visualizations.

**Memory issues with large datasets**

For datasets with millions of rows, consider sampling:
```python
df = pd.read_csv(filepath).sample(n=100000, random_state=42)
```

**Permission errors on Windows**

Run terminal/command prompt as administrator if you encounter permission issues.

## Deactivating Virtual Environment

When finished:
```bash
deactivate
```

## Future Installations

For subsequent runs, you only need to:
1. Activate the virtual environment
2. Run the script

No need to reinstall dependencies unless you delete the virtual environment.

## License

Open source and available for educational and personal use.

## Notes

- All visualizations use professional color schemes optimized for both screen and print
- Statistical calculations follow standard practices for data analysis
- The script is designed to work with any CSV dataset structure
- Generated plots are publication-ready at 300 DPI resolution
