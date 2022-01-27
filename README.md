# README_PUMBAA# PUMBAA

PUMBAA (Version 2.0) is a MATLAB software created in 2021 within the [Sidorov Lab](http://sidorovlab.org/) at Children's National Medical Center. It's initial use was to run multidimensional analysis on the behavioral battery of angelman syndrome mice. Based on the
behavioral battery the goal was to distinguish between Angelman syndrome and Wild-Type Mice based solely on the combination of behavioral values. This was accomplished successfully and PUMBAA has since then been modified to perform the same multidimensional analysis 
on other behavioral data sets to find the correlations between groups.

## Multidimensional Analysis 
Multidimensional Analysis is a several step process that
## Installation

MATLAB can be installed [here](https://www.mathworks.com/login?uri=%2Fmwaccount%2F). After creating a MathWorks Account you may view additional licenses and select the most recent license for the MATLAB software. 

After the file is installed, in the file browser, create a separate folder for all MATLAB-related content.

```bash
pip install foobar
```

## Accessing PUMBAA

If you have the PUMBAA.mlapp file already, move it into the MATLAB folder on your computer

MATLAB is a system that functions based on items in a select pathway so after opening the program select the 'Home' tab in the upper left corner and navigate to the box that says, "Environment". Within this box select 'set path' and direct it towards your MATLAB folder containing PUMBAA.mlapp. You can check the bar underneath to ensure the right path was selected.

## Data Requirements 
For PUMBAA to function properly data must be organized in a particular way.

1. Place data (raw or pre-standardized) into a separate excel file (xls or xlsx). 
2. The first two rows are used for column headers with emphasis on the first row 
3. Label sex column 'sex' and each animal 'male' or 'female'
4. Numerical data points must begin in the third row of data. 
5. The last row should also be used for genotype denoting them as 1 for WT and 2 for the experimental group

## Utilizing PUMBAA

After these requirements are met type PUMBAA into the workspace to open the app and it will open.
```matlab
 
PUMBAA 

```
Now that the app is open you can select you excel file of raw data  or pre-standardized data. A pop up window will appear indicating which file has been selected. 

### Standardization

The first checkbox is only to be used if you decide to isolate which measures you would like to standardize. Otherwise, it is fine to leave it unchecked.

After clicking the first listbox it should have listed all the columns that can be standardized. By using 'ctrl + left mouse click' you can select whichever columns you prefer to standardize by sex. All remaining columns will be standardized based on all values in the column.

Selecting the 'Standardization' button will then standardize your data and place an identical sheet, to the original, with standardized values within your MATLAB folder.

### Principal Component Analysis

If you are already aware of how many principal components you would like to utilize then you may proceed to the next section. If not, clicking the PCA button will display a scree plot to aid with this selection. (The most ideal number of principal components is where the graph makes a sharp turn in the data).%%Revise 

### K-Means Clustering and Validation
Using the spinner on the right you may select the value of K for K-Means clustering (how many groups will the data be divided into).

 Using the spinner on the left you can select how many principal components will be used, values ranging from two to three. After selecting both of these click the 'Complete Multidimensional Analysis' button and several 2 or 3-D graphs will display your results. 
The excel file produced will have all of the PCA values uploaded for future analytical referencing.
