[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```python
import numpy as np
import seaborn as sns
from matplotlib import pyplot as plt
import random


samples = [random.random() for _ in range(1000)]
counts = pd.Series(sample).value_counts().sort_index()
densities = counts / len(counts)
accum_densities = np.add.accumulate(densities)

sns.set()
fig, ax = plt.subplots(1, 2, figsize=(10, 5), dpi=100)
ax[0].plot(densities.index, densities)
ax[0].set_title('PDF')
ax[1].plot(accum_densities.index, accum_densities, color='green')
ax[1].set_title('CDF')
fig.savefig('random_pdf_and_cdf.png')
```
![](/img/random_pmf_and_cdf.png)