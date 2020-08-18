## scipy 库
```py
linear_regression = stats.linregress(x=nyc.Date,
                                     y=nyc.Temperature)
```

## seaborn库
```py
sns.set_style('whitegrid')
axes = sns.regplot(x=nyc.Date, y=nyc.Temperature)

axes.set_ylim(10, 70)


```
