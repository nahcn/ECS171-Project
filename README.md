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

