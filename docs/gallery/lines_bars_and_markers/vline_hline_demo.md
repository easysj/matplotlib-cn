# hlines和vlines

此示例展示了hlines和vlines的功能。

![hlines和vlines图例](/static/images/gallery/sphx_glr_vline_hline_demo_001.png)

```python
import matplotlib.pyplot as plt
import numpy as np


t = np.arange(0.0, 5.0, 0.1)
s = np.exp(-t) + np.sin(2 * np.pi * t) + 1
nse = np.random.normal(0.0, 0.3, t.shape) * s

fig, (vax, hax) = plt.subplots(1, 2, figsize=(12, 6))

vax.plot(t, s + nse, '^')
vax.vlines(t, [0], s)
# By using ``transform=vax.get_xaxis_transform()`` the y coordinates are scaled
# such that 0 maps to the bottom of the axes and 1 to the top.
vax.vlines([1, 2], 0, 1, transform=vax.get_xaxis_transform(), colors='r')
vax.set_xlabel('time (s)')
vax.set_title('Vertical lines demo')

hax.plot(s + nse, t, '^')
hax.hlines(t, [0], s, lw=2)
hax.set_xlabel('time (s)')
hax.set_title('Horizontal lines demo')

plt.show()
```

## 下载这个示例

- [下载python源码: vline_hline_demo.py](https://matplotlib.org/_downloads/vline_hline_demo.py)
- [下载Jupyter notebook: vline_hline_demo.ipynb](https://matplotlib.org/_downloads/vline_hline_demo.ipynb)