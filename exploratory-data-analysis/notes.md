# Exploratory Data Analysis

## Misc Notes

- the foundations for data science are formed by John W. Tukey
- simple plots along with summary statistics

## Elements of structured data

- much of data is unstructured
- two basic types of structured data
	- numeric
	- categorical
- ordinal data (1, 2, 3, 4, 5) ordered categories

## Rectangular Data

- the "label" is also called the "outcome" or the "target". It's the dependent variable

### Data frames and indexes
- in R, the basic rectangular data structure is a `data.frame` object
- `data.table` and `dplyr` for multilevel index in R

**Terminology Differences**
Data scientists: _features_ are used to predict a _target_
Statisticians: _predictor variables_ are used to predict _response_ or _dependent variable_

_Sample_: Computer scientists use _sample_ to mean a single row, stats people use it for a collection of rows

### Nonrectangular Data Structures
Examples of non-rectangular data structures:
- time series data
- spatial data 
- graph (network) data structures
  - used to represent physical, social and abstract relationships
  - example: a social network, distribution hubs
  - useful for recommendations systems and network optimization
- rectangular data is the fundamental building block of predictive modeling

**KEY IDEAS**
- The basic structure in DS is the rectangular matrix
- Terminology can be different between disciplines

## Estimates of Location
A "typical value" for each feature is an estimate of where most of the data is located (central tendency)

**Key Terms**
Mean - the average
Weighted Mean - the sum of all values times a weight divided by the sum of the weights
Median - the 50th percentile
Percentile - The value such the _P_ percent of the data lies below AKA quantile
Weighted median - the value such that one-half of the sum of the weights lies above and below the sorted data
Trimmed mean - the average of all values after dropping a fixed number of extreme values 
Robust - not sensitive to extreme values
Outlier - a data value that is very different from most of the data

_"statisticians estimate, data scientists measure"_

### Mean
$Mean = \bar{x} = \frac{\sum_{i=1}^{n}}{n}$

### Median and Robust Estimates
### Outliers
### Example: Location Estimates of Population and Murder Rates

## Estimates of Variability

### Standard Deviation and Related Estimates
### Estimates based on Percentiles
### Example: Variability Estimates of State Population

## Exploring the Data Distribution

### Percentiles and Boxplots
### Frequency Tables and Histograms
### Density Plots and Estimates

## Exploring Binary and Categorical Data

### Mode
### Expected Value
### Probability

## Correlation

### Scatterplots

## Exploring Two or More Variables

### Hexagonal Binning and Countours (Plotting Numeric Versus Numeric Data)
### Two Categorical Variables
### Categorical and Numeric Data
### Visualizing Mutiple Variables

## Summary






