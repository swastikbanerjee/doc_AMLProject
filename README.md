# The `mysticML` Library

[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)

# Authors
### Shiladitya Sarkar \ Swastik Banerjee \ Abhinav Bammidi

## Overview

The `mysticML` library is a Python library designed for automating the Machine Learning Pipeline.
Boost productivity by skipping the boring part!

Let `mysticML` handle that for you. 

## Features

- Easy-to-use interface with robust functionality.
- Integration with popular libraries such as `scikit-learn`, `NumPy` and `pandas`.

## Installation

You can install the library using pip:

```bash
#install the library
pip install mysticML
#upgrade the library to the latest version
pip install --upgrade mysticML

```

## Getting Started
```bash
import mysticML
from mysticML import Preprocess

preprocess = Preprocess(df) #where df contains the target dataframe
                            #type pandas.DataFrame

preprocess.fit(target : str,
               combo : str, 
               duplicate : bool, 
               outlier : bool, 
               impute : bool, 
               transform : bool, 
               encode : bool, 
               feature_sel : bool, 
               feature_ext : bool, 
               sampling : bool) -> pandas.DataFrame #returns the preprocessed dataframe.

```

# Parameters
`target`: Accepts the name of the target column. When ignored, the last column is assumed to be the target column by default. 

`combo`: Values accepted `basic` | `intermediate` | `advanced`, representing different levels of pre-processing. Each level entails a custom set of procedures for execution on the target dataframe.

  - `basic`: `duplicate`, `outlier`, `impute`
  - `intermediate`: `duplicate`, `outlier`, `impute`, `transform`, `encode`
  - `advanced`: `duplicate`, `outlier`, `impute`, `transform`, `encode`, `feature_sel`, `feature_ext`, `sampling`
    
    default : `combo = advanced`

`duplicate`: Accepts a boolean value to determine the execution of the duplicate removal class.

`outlier`: Accepts a boolean value to specify the inclusion or exclusion of the outlier removal class.

`impute`: Accepts a boolean value to determine whether the imputation class should be executed.

`transform`: Accepts a boolean value, indicating the execution status of the transformation class.

`encode`: Accepts a boolean value to determine the execution of the encoding class.

`feature_sel`: Accepts a boolean value to dictate the execution status of the feature selection class.

`feature_ext`: Accepts a boolean value to specify the inclusion or exclusion of the feature extraction class.

`sampling`: Accepts a boolean value to determine the execution of the sampling class.


## To view the report
```bash
preprocess = Preprocess(df)
preprocess.fit()
preprocess.report_ #prints the report of what has been done on the dataset provided.
```

## Tutorials

#### On the standard Iris dataset
```bash
from mysticML import Preprocess
import pandas
from sklearn import datasets

# Load the Iris dataset (classification)
iris = datasets.load_iris()
iris_df = pandas.DataFrame(data=iris.data, columns=iris.feature_names)
iris_df['target'] = iris.target

#create an object of type Preprocess
preprocess = Preprocess(iris_df)
#call the fit function
iris_df_preprocessed = preprocess.fit()
```

#### On the standard California Housing dataset
```bash
from mysticML import Preprocess
import pandas
from sklearn import datasets

#Load the california housing dataset (regression)
california_housing = datasets.fetch_california_housing()
california_df = pandas.DataFrame(data=california_housing.data, columns=california_housing.feature_names)
california_df['target'] = california_housing.target

#create an object of type Preprocess
preprocess = Preprocess(california_df)
#call the fit function
california_df_preprocessed = preprocess.fit()
```

## Mail your queries, suggestions or collaboration request to
writetoshiladitya@gmail.com | 
swastikbanerjee2001@gmail.com | 
bammidiabhinav@gmail.com

