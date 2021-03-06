[![ci-cd](https://github.com/UBC-MDS/numeric_edahelper/actions/workflows/ci-cd.yml/badge.svg)](https://github.com/UBC-MDS/numeric_edahelper/actions/workflows/ci-cd.yml)

# numeric_edahelper

Data scientists often spend alot of time preprocessing data to extract useful parts for their analysis. The numeric_edahelper package is a package that aims to streamline Exploratory Data Analysis, specifically for numeric data in datasets. The goal is to simplify some common and repetitive tasks during EDA and data preprocessing for data analysts, as well as add value to their workflow by presenting some useful insights in a quick manner (just calling our functions), such as displaying highly-correlated variables and outliers. 

The package includes functions which can complete the following tasks:

- Display some useful statistics
- Detect outliers
- Deal with missing values
- Check for correlation between features

## Installation

```
pip install numeric_edahelper
```

## Usage

An example of how to use `numeric_edahelper` in Python:
```
import pandas as pd
import numpy as np

from numeric_edahelper.overview import overview
from numeric_edahelper.missing_imputer import missing_imputer
from numeric_edahelper.flag_outliers import flag_outliers
from numeric_edahelper.get_correlated_features import get_correlated_features

df = pd.DataFrame({'col1': [-100,-200, 1,2,3,4,5,6,7,8,9,np.nan, 1000], 
                   'col2': [1,2,3,4,5,6,7,8,9,10,11,12,13],
                   'col3': [-50, 1,2,3,4,5,6,7,8,9,10,11,50000]})
overview(df, quiet=False)
missing_imputer(df, method="median")
flag_outliers(df, threshold=0.2)
get_correlated_features(df, threshold=0.7)
```

## Function descriptions

- `overview`: This function calculates common descriptive statistical values of in the input data. Users can choose the extent of information that is returned and have the option to use the function as a means to create statistical variables to be used elsewhere in the environment.
- `flag_outliers`: This function helps to display numeric variables which contain outliers that exceed a certain user-specified threshold percentage, using the interquartile range method. Users can then take note of these variables with high percentage of outliers and decide what to do with the variable(s).
- `missing_imputer`:This function aims to detect missing values in the numeric data frame and using strategies including drop, mean or median to drop missing values or to replace them with the mean or median of other values in the same column.
- `get_correlated_features`:This function will get pairs of features which have correlation above a threshold value. We can specify if we want to check only the magniture of correlation value or we also want to consider sign (positive/ negative).

## Documentation

The official documentation is hosted on [`Read the Docs`](https://numeric-edahelper.readthedocs.io)

## Similar Work

In the Python open-source ecosystem, there exists some useful packages that already  tackle EDA and preprocessing, but our goal is to make it even more light-weighted, fast and specifically tailored to present numeric EDA insights. One popular and useful package that can generate EDA reports is: 

- [`pandasprofiling`](https://github.com/pandas-profiling/pandas-profiling)


## Contributors

We welcome all contributions and the current main contributors are:

-   Anupriya Srivastava 
-   Jiwei Hu 
-   Michelle Wang 
-   Samuel Quist


## License

Licensed under the terms of the MIT license.

## Credits

`numeric_edahelper` was created with [`cookiecutter`](https://cookiecutter.readthedocs.io/en/latest/) and the `py-pkgs-cookiecutter` [template](https://github.com/py-pkgs/py-pkgs-cookiecutter).

