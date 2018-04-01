[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> First babies are on average 0.125 pounds lighter than other babies. This difference is 0.089 standard deviations—more than the 0.029 deviations for the difference in pregnancy length, but still not very large.

```python
import os
import numpy as np
path = os.path.expanduser('~/Documents/Projects/Metis/Prework/ThinkStats2-master/code')
os.chdir(path)
import nsfg


def cohens_d(group1, group2):    
    diff_in_means = group1.mean() - group2.mean()
    pooled_var = len(group1) * group1.var() + len(group2) * group2.var()
    pooled_var /= len(group1) + len(group2)
    pooled_std = np.sqrt(pooled_var)
    return diff_in_means / pooled_std


preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
first_pregs = live[live.birthord == 1]
other_pregs = live[live.birthord != 1]

diff = first_pregs.totalwgt_lb.mean() - other_pregs.totalwgt_lb.mean()
effect_size = cohens_d(first_pregs.totalwgt_lb, other_pregs.totalwgt_lb)

print(f'Mean weight difference: {diff:.3f} lbs')
print(f"Cohen's d: {effect_size:.3f}") 
```
```
Mean weight difference: -0.125 lbs
Cohen's d: -0.089
```