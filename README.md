# ERROR

![error](./Captura%20de%20Tela%202023-10-29%20às%2016.41.21.png)

``` text

---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
/Users/jersonbrito/dev/curso-dados/titanic.ipynb Célula 13 line 1
----> 1 df.corr()

File ~/dev/curso-dados/.venv/lib/python3.10/site-packages/pandas/core/frame.py:10704, in DataFrame.corr(self, method, min_periods, numeric_only)
  10702 cols = data.columns
  10703 idx = cols.copy()
> 10704 mat = data.to_numpy(dtype=float, na_value=np.nan, copy=False)
  10706 if method == "pearson":
  10707     correl = libalgos.nancorr(mat, minp=min_periods)

File ~/dev/curso-dados/.venv/lib/python3.10/site-packages/pandas/core/frame.py:1889, in DataFrame.to_numpy(self, dtype, copy, na_value)
   1887 if dtype is not None:
   1888     dtype = np.dtype(dtype)
-> 1889 result = self._mgr.as_array(dtype=dtype, copy=copy, na_value=na_value)
   1890 if result.dtype is not dtype:
   1891     result = np.array(result, dtype=dtype, copy=False)

File ~/dev/curso-dados/.venv/lib/python3.10/site-packages/pandas/core/internals/managers.py:1656, in BlockManager.as_array(self, dtype, copy, na_value)
   1654         arr.flags.writeable = False
   1655 else:
-> 1656     arr = self._interleave(dtype=dtype, na_value=na_value)
   1657     # The underlying data was copied within _interleave, so no need
   1658     # to further copy if copy=True or setting na_value
...
-> 1715     result[rl.indexer] = arr
   1716     itemmask[rl.indexer] = 1
   1718 if not itemmask.all():

```
