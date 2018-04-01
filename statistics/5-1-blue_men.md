[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 34.27%

```python
from scipy import stats, constants

height_cdf = stats.norm(loc=178, scale=7.7).cdf

def to_cm(feet, inches):
    return (feet * 12 + inches) * constants.inch * 100

in_range = height_cdf(to_cm(6, 1)) - height_cdf(to_cm(5, 10))

print(f'{in_range:.2%} of men are in this range.')
```
```
34.27% of men are in this range.
```