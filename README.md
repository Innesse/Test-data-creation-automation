# Test Data Generation for Machine Learning

This Python function, `create_test_data`, generates synthetic test data for machine learning tasks in pricing and demand prediction. It is useful for simulating scenarios where you want to test your machine learning models against varying product prices, quantities, and elasticities.

## Overview

The `create_test_data` function takes various parameters and produces a Pandas DataFrame with the following columns:

- `Product Name`: The name of the product, numbered from 1 to N (N = number of products).
- `Elasticity`: Elasticity values to test with each product.
- `Price`: The product's price, which dynamically changes according to predefined elasticity.
- `Quantity`: The quantity of the product purchased.
- `Revenue`: The revenue generated from each transaction.
- `Customer`: Randomly selected customer names for each transaction.
- `Date`: Randomly selected transaction dates within the specified date range.
- `Year`: The year of the transaction.

## Function Parameters

- `price_5_percentile`: 5% percentile of prices in the training data.
- `price_95_percentile`: 95% percentile of prices in the training data.
- `quantity_5_percentile`: 5% percentile of quantities in the training data.
- `quantity_95_percentile`: 95% percentile of quantities in the training data.
- `n_products`: Number of products in the test data.
- `n_transactions`: Number of transactions for each product in the test data.
- `n_customers`: Number of customers in the test data.
- `elasticity`: A list of elasticity values to test with each product.
- `start_date`: Start date for transaction date generation.
- `end_date`: End date for transaction date generation.

## Additional Functions
`date_list(lst, n)`
This function slices a list into n sublists, sorts them, and then merges them back into a single sorted list of dates.

`random_date(start, end)`
This function generates a random datetime between two specified datetime objects.

These functions are used internally in the create_test_data function to generate transaction dates and sort them.

## Usage

You can use this function to generate synthetic test data for your machine learning projects by providing the necessary parameters. Here's an example of how to use it:

```python
import pandas as pd
import numpy as np
from datetime import timedelta
from datetime import datetime
import random
from random import randrange

# Define your parameters
price_5_percentile = 10  # Example values
price_95_percentile = 100
quantity_5_percentile = 5
quantity_95_percentile = 50
n_products = 10
n_transactions = 1000
n_customers = 50
elasticity = [0.2, 0.5, 1.0]
start_date = '01/01/2023'
end_date = '12/31/2023'

You can specify different brands, currencies, countries, and markets using the `data_brands` parameter. This allows you to test the impact of these factors on your machine learning predictions.

```python
data_brands = [
    {'Brand': 'Air Defence Show',
     'Currency': 'UAH',
     'Brand country': 'Ukraine',
     'Brand market': 'Public admin, defence & social security',
     },
    {'Brand': 'Best Tanks Show',
     'Currency': 'USD',
     'Brand country': 'USA',
     'Brand market': 'Public admin, defence & social security',
     }
]

# Run 

# Generate test data
test_data = create_test_data(price_5_percentile, price_95_percentile, quantity_5_percentile, quantity_95_percentile, n_products, n_transactions, n_customers, elasticity, start_date, end_date)

# Now you can use this data for your machine learning experiments.
```

## Author
[Innesse](https://github.com/Innesse) 


## Acknowledgments
Special thanks to open-source libraries used in this project.
