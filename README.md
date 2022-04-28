## Lab 1 Loading Data

### Common Data Formats
1. Downloadable files
* Comma-separated-values (CSV) or text files (txt) more generally 
* and Excel or XLS files
* Spatial data: JSON, GeoJSON
2. API (Application Program Interface)
3. Databases 

### API
* `DataFrame.head([n])` Return the first n rows.
* `DataFrame.copy([deep])` Make a copy of this object's indices and data.
* `DataFrame.at` Access a single value for a row/column label pair.
* `DataFrame.loc` Access a group of rows and columns by label(s) or a boolean array.
* `DataFrame.iloc` Purely integer-location based indexing for selection by position.
* `DataFrame.groupby([by, axis, level, ...])` Group DataFrame using a mapper or by a Series of columns.
* `DataFrame.describe([percentiles, include, ...])` Generate descriptive statistics.
* `Series.astype(dtype[, copy, errors])` Cast a pandas object to a specified dtype dtype.
* `Series.unique()` Return unique values of Series object.
* `Series.nunique([dropna])` Return number of unique elements in the object.
* `Series.value_counts([normalize, sort, ...])` Return a Series containing counts of unique values.

### Notes:
1. Download Data From URL

```{python}
import urllib # use urllib mobule for web requests
url = 'web_address'
dataDir = 'local data folder to save data' 
urllib.request.urlretrieve(url, dataDir)
```
2. Pay attention to the slice order when try to change part of elements in a column

`df['taerget_column'][df.taerget_column != 'VALUE'] = 'AIM_VALUE' ` works

`df[df.taerget_column != 'VALUE']['taerget_column'] = 'AIM_VALUE' ` dose not work

3. To avoid error like `ValueError: invalid literal for int() with base 10:` in converting data type, try convert as following order `str-->float-->int`.

(basic geodata plot)
