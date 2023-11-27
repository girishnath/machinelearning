# What Drives the Price of a Car?
This analysis was performed on a [dataset](data/vehicles.csv) of 420K used car sales. The exploratory analysis, modeling, findings and next steps are available in a [Jupyter Notebook](used-car-pricing.ipynb).

# Methodology
The CRISP-DM Methodology was used for this exercise. In the Data Understanding and Data Preparation steps, several insights were gained and we were able to drop columns such as `id`, `region` and `VIN`. The data was also cleaned up to remove outliers, and some columns with high cardinality such as `state` were reduced to a smaller cardinality. In the modeling step, grid searches were perfomed using various hyperparameters and estimators. All of this enabled us to draft a Deployment Report for the customer.

# Major findings
While the details are available in the [Jupyter Notebook](used-car-pricing.ipynb), the major takeaways were:

*   A Ridge Model and Linear Regression Model performed equally well on the data set. Ridge Model was selected due to the additional hyperparameters that can be tuned.
*   The major factors influencing used car pricing were identified to be Year, Model/Manufacturer and some auxiliary factors such as number of cylinders and transmission type. While the age of the car played a major role, the odometer readings did not seem correlated to the price at all.

# Next steps

While an initial model was selected, the following additional analyses should be performed:
*   The data should be clustered, and the modeling should be rerun on each cluster. This should produce a better result since the features that are important in the lower end of the market is not necessarily important in the higher end of the market.
*   To be more precise, assuming we have enough data, separate models should be created for the top vehicle models (such as corvette).
*   While this analysis focused on the price drivers, a parallel analysis on volume drivers (number of cars sold) will yield additional insights to the customer.
