# Kaggle-NYCTaxi

This repository contains my solution for the Kaggle competition <a href = "https://www.kaggle.com/c/nyc-taxi-trip-duration"> New York City Taxi Trip Duration</a>. This solution ranked 49 out of 1257.

The goal of this competition was to predict the trip duration of taxi trips in New York City in the first half of 2016. My solution focussed mainly on the feature engineering part.

The exploratoy data analysis, the feature engineering and the model fitting were all done in the notebook <a href = "https://github.com/pklauke/Kaggle-NYCTaxi/blob/master/Predictor.ipynb">Predictor</a>. Important given features were the timestamp, pickup and dropoff coordinates and the vendor id of a respective taxi trip. 

Some of the engineered features were features extracted from the timestamp. Many others were created by the pickup and dropoff coordinates. E.g. geospatial and temporal aggregations using the clustering algorithm <a href = "http://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html">KMeans</a> or using a <a href= "http://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html">principal component analysis</a>. Quite uniquely I did some work to estimate the average speed trips will have on their (fastest route) streets at the respective time of day and day of week. This estimation was done using the <a href= "https://www.kaggle.com/c/nyc-taxi-trip-duration/discussion/37033">fastest route dataset</a>.

The algorithm used was the extremely fast gradient boosted library <a href = "http://lightgbm.readthedocs.io/en/latest/"> LightGBM</a>. This algorithm was trained several times using different random seeds. The predictions of the several runs were averaged for the final submission.
