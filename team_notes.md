# ECS171-Project

## Data Management

We processed the `crime_and_incarceration_by_state.csv` and the Jupyter notebook
we used is in the `data_management` directory. In the file we left notes on what
we did and some reasoning. We dropped null values, encoded columns, normalized
numerical features, and dropped correlated features. Also, before normalizing
the columns we changed the counts for different types of crimes to be the percentage
of the state populations. As you work on the next parts, if you need anything changed,
let us know.

To get the processed data, run the `CrimeAndIncarceration.ipynb` file in
the `data_management` directory. This will create a new csv file in the
`processed_datasets` directory that you can import and use.

Note: We did not work with the `prison_custody_by_state.csv` and the
`ucr_by_state.csv` datasets because `crime_and_incarceration_by_state` is already
a combination of their data.

## UI/UX

Our work begins under the section titled `Polynomial Regression Formulation`. It was difficult finding a correlation between `prisoner_count` and any other features in the current dataset so we read in a new csv file: `poverty_rate_per_year.csv`, which includes data about the poverty rate in the US from 1989 to 2019. After performing some cleaning on this data set, we added a new column, `poverty_rate`, to the dataset cleaned by the Data Management team. Note that we added this coulumn to the dataset that had not yet been encoded and normalized. 

We found it difficult to find data on the poverty rates for each state for each year from 2001 to 2016, so we assigned the `poverty_rate` for each state to be the US poverty rate for that particular year (All states in a particular year have the same poverty rate)

Plotting various combinations of data, we found that there was no consistent correlation between the same feature combinations for different states. Thus, we decided to use polynomial regression (as opposed to linear), which better maps real world data.

The function `performPolyReg()` takes in three parameters: state, predictor, and predicted. It trys polynomial regression on various degrees (1-10) and returns the best performing degree along with its root mean squared error. The funciton plots the polynomial regression line on the scatter plot as well to help visualize the information.
