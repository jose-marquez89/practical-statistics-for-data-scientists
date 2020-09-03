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
![Mean](img/mean.png)

Trimmed mean cuts off _p_ values from both sides of all values, sorted. Helps to
control extreme values
![Trimmed Mean](img/trimmedMean.png)

Weighted mean is the sum of weights times values divided by sum of weights. This
helps when particular variables are over or underrepresented.
![Weighted Mean](img/weightedMean.png)

### Median and Robust Estimates
- The median is less sensitve to the data than the mean.
- When there are an even number of data values, the median is the average of
  the two values that divide the data set into upper and lower halves.

Why use the median?
- remember "Bill Gates walks into a bar, the average person is now a millionaire"
- this type of thing doesn't affect the median

Note: _You can also compute a weighted median_ (look this up)
### Outliers
- always make an effort to investigate outliers
- sometimes an outlier will be the result of erroneous data
- the mean is more sensitive to erroneous data, whereas the median is not
  affected nearly as much

**Anomaly Detection**
In anomaly detection, outliers _are_ the points of interest, the rest of the data
just informs what is normal

The **trimmed mean** is a nice compromise to consider when outliers are present.
it's robust enough to escape major influence from outliers, but also uses
more of the data

There are other **more robust metrics** that can be efficient but if the data
is large enough, it may not make that much of a difference

### Example: Location Estimates of Population and Murder Rates
**Computing mean in R**
```R
> state <- read.csv('state.csv')
> mean(state[['Population']])
[1] 6162876
> mean(state[['Population']], trim=0.1)
[1] 4783697
> median(state[['Population']])
[1] 4436370
```

**Pandas**
```python
state = pd.read_csv('state.csv')
state['Population'].mean()
trim_mean(state['Population'], 0.1)
state['Population'].median()
```

**Weighted mean in R**
This uses the `matrixStats` package
```R
> weighted.mean(state[['Murder.Rate']], w=state[['Population']])
[1] 4.445834
> library('matrixStats')
> weightedMedian(state[['Murder.Rate']], w=state[['Population']])
[1] 4.4
```

**Weighted mean with pandas and numpy**
```python
np.average(state['Murder.Rate'], weights=state['Population'])
wquantiles.median(state['Murder.Rate'], weights=state['Population'])
```
**KEY IDEAS**
- the basic metric for location is the mean but it can be sensitive to outliers
- other metrics like trimmed mean and median are more robust

## Estimates of Variability
- **variability** is at the heart of statistics
- **dispersion** is how tightly clustered or spread apart the data is

**KEY TERMS**
Deviations - the difference between the observed values and the estimate of
location
Variance - The sum of squared deviations from the mean divided by n – 1 where n is the number of data values (AKA mean squared error)
Standard deviation - the square root of the variance
Mean absolute deviation - The mean of the absolute values of the deviations from the mean (AKA l1 norm, Manhattan norm)
Range - the difference between the largest and smallest value in the datset
Order statistics - metrics based on the sorted data values (AKA ranks)
Percentile - The value such that P percent of the values take on this value or less and (100–P) percent take on this value or more (AKA quantile)
Interquantile range - The difference between the 75th percentile and the 25th percentile (AKA IQR)

### Standard Deviation and Related Estimates
- a deviation is a difference between the estimate of location and the observed
data
- the deviations tell us how dispersed the data is around the central value

**Mean absolute deviation**
this is the average of the absolute values of the deviations
mad = ![mad](img/meanAbsDev.png)
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
