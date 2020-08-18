## scipy库
```py
from scipy import stats
linear_regression = stats.linregress(x=nyc.Date,
                                     y=nyc.Temperature)
                                     
                                   
linear_regression.slope
linear_regression.intercept
linear_regression.slope * 2019 + linear_regression.intercept
```
