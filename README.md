# README_PUMBAA# PUMBAA

PUMBAA (Version 2.0) is a MATLAB software created in 2021 within the [Sidorov Lab](http://sidorovlab.org/) at Children's National Medical Center. It's initial use was to run multidimensional analysis on the behavioral battery of angelman syndrome mice. The goal was to use data from the behavioral battery to accurately distinguish between Angelman syndrome and Wild-Type Mice based solely on the combination of behavioral values. This was accomplished successfully and PUMBAA has since then been modified to perform the same multidimensional analysis on other behavioral data sets to find the correlations between groups.

## Multidimensional Analysis 
<img width="469" alt="Multidimensional Analysis Picture" src="https://user-images.githubusercontent.com/98532332/151368720-e7681a2e-5120-48e2-992c-ef665fcf34fd.png">
Multidimensional Analysis is a several step process that includes the use of analytical processes such as Standardization, Principal Component analysis, K means Clustering and Validation. The image above displays the pipeline PUMBAA utilizes in order to complete multidimensional analysis. 
The process begins with standardization where the entire data set is assigned new values for each individual point as they are relative to the mean and one standard deviation. Next this is followed by Principal Component Analysis(PCA). With PCA the new standardized data set is grouped into a principal component that explain the most amount of variance/correlation between data metrics. The second principal component will attempt to do the same explaining the second amount of variance and so on. Folowing PCA, K-Means clustering groups the data points derived from PCA into distinguishable groups. The amount of groups created is represented by the value of k (which most commonly for our purposes is 2).

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
2. The firstrow shoudl contain columnar headers(i.e. weight, ID #, Sex, etc.) 
3. Label sex column 'sex' and each animal 'male' or 'female'
4. Numerical data points must begin in the third row of data. 
5. The last row should also be used for genotype denoting them as 1 for WT and 2 for the experimental group

## Utilizing PUMBAA

![Load Data Picture](https://user-images.githubusercontent.com/98532332/154345074-88447cdc-ea89-422f-8224-ca2448f54b54.png)
<img width="256" alt="image" src="https://user-images.githubusercontent.com/98532332/163734954-41062d54-cf0d-4d57-b355-192a403657b9.png">

After these requirements are met type PUMBAA into the workspace to open the app and it will open.
```matlab
 
PUMBAA 

```
Now that the app is open you can select you excel file of raw data  or pre-standardized data. You may have to switch the search to include all file types to access  the excel or csv. A pop up window will appear indicating which file has been selected, the program **will not** continue unless "ok" is selected on this pop-up box 


### Standardization

![PUMBAA APP Picture - Copy (3)](https://user-images.githubusercontent.com/98532332/154347410-90409c81-2989-4ab7-9d22-8ce1f67065b8.png)

The check box tited "Data is already standardized" allows you to skip the standardization process in the GUI. If this applies to your data you may proceed with Principal Component Analysis.

After clicking the first listbox it should have listed all the columns that can be standardized. By using 'ctrl' + 'left mouse click' you can select whichever columns you prefer to standardize by sex. All unselected columns will be standardized per each behavioral mesurement.

If you prefer to use a reduced list of measures you may select the "select behaviors" checkbox. This places all selected values in the "Selected behaviors" listbox that functions identically to the original list box.

Selecting the 'Standardization' button will then standardize your data and place an identical sheet, to the original, with standardized values within your MATLAB folder.


### Principal Component Analysis

![PUMBAA APP Picture - Copy (4)](https://user-images.githubusercontent.com/98532332/154350329-5b597e66-b491-4c0f-ad1c-d7c0ca538b61.png)
![image](https://user-images.githubusercontent.com/98532332/163735071-f9b6ce10-5bb5-42aa-a5c8-92f7fedb1762.png)

If you are already aware of how many principal components you would like to utilize then you may proceed to the next section. If not, clicking the PCA button will display a scree plot to aid with this selection. The optimal number of principal components will be indicated by a sharp turnin the graphed values. Typicaly this value is two in order to account for a majority of the variance across principal components. 

### K-Means Clustering and Validation

![PUMBAA APP Picture - Copy (5)](https://user-images.githubusercontent.com/98532332/154350952-e6aa85c0-5b04-4b70-ab7f-404bc657df7e.png)


Using the spinner on the right you may select the value of K for K-Means clustering (how many groups will the data be divided into).

 Using the spinner on the left you can select how many principal components will be used, values ranging from two to three. After selecting both of these click the 'Complete Multidimensional Analysis' button and several 2 or 3-D graphs will display your results. 
The excel file produced will have all of the PCA values uploaded for future analytical referencing.
