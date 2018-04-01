[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

```python
import numpy as np
import seaborn as sns
from matplotlib import pyplot as plt
import os
path = os.path.expanduser('~/Documents/Projects/Metis/Prework/ThinkStats2-master/code')
os.chdir(path)
import nsfg


# Get the data.
resp = nsfg.ReadFemResp()

# Calculate counts.
hh_type_counts = resp.numkdhh.value_counts()
children_per_type_counts = hh_type_counts * hh_type_counts.index

# Calculate and plot PMF.
options = dict(bins=range(0,7), normed=True, alpha=0.5, align='left')
hh_types = children_per_type_counts.index.data

sns.set()
fig = plt.figure(dpi=100)
axes = plt.axes(ylabel='PMF', xlabel='Number of children')
unbiased_probs, num_children, _ = plt.hist(
        hh_types, weights=hh_type_counts, label='Unbiased', **options)
biased_probs, num_children, _ = plt.hist(
        hh_types, weights=children_per_type_counts, label='Biased', **options)
plt.legend()
fig.savefig('children_hist.png')

# Calculate means.
unbiased_mean = unbiased_probs @ hh_types
biased_mean = biased_probs @ hh_types
print(f'Unbiased mean: {unbiased_mean:.3f}')
print(f'Biased mean: {biased_mean:.3f}')
```
```
Unbiased mean: 1.024
Biased mean: 2.404
```
![](/img/children_hist.png)

