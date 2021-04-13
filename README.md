# Veri Analizi Kaynak

- ## `NaN` değer elde etmek:

```python
import math
import numpy as np

float("nan")
math.nan
np.nan
```

```python
>>> math.isnan(np.nan), np.isnan(math.nan)
(True, True)

>>> math.isnan(y_with_nan[3]), np.isnan(y_with_nan[3])
(True, True)
```

## Kaynaklar

[Real Python](https://realpython.com/)
