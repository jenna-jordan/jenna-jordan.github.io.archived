---
title: Useful Pandas Snippets
published: # true / false
permalink: /useful-panas-snippets
toc: true
toc_sticky: true
header:
    image: assets/images/header_short-title.jpg
    caption: # optional
tags:
  - IS452
  - Python
---

So ever since Thanksgiving Break, I have been learning Pandas so that I can use it for my final project (Phase 1 of the IRDB). But, Pandas is kind of weird. Pandas is what happened when Python and R had a baby, except only momma Python got sole custody of baby Pandas. Also NumPy is somehow involved... maybe as Pandas older sibling, and it's unclear (to me) if R is NumPy's father as well or Python had a baby with some other language before it's affair with R. Regardless of the weird metaphor, Pandas is the mess I've been learning how to use and cope with for the past few weeks, and I have found myself repeating certain functions/methods. So for future referral, here they are.

## For importing & exporting csv files

Import a csv file as a data frame:

```python
dfName = pd.read_csv('Folder/filename.csv')
```

Export a dataframe as a csv file:

```python
dfName.to_csv('Folder/filename.csv', encoding='utf-8', index=False)
```

## For trimming down dataframes

To drop columns:

```python
dfName.drop(columns=['column1', 'column2', <...>], inplace=True)
```

To drop duplicates (ie rows in which all info is identical to another row)

```python
dfName.drop_duplicates(inplace=True)
```

## For investigating data in dataframes

To find maximum length of a (string/object) column:

```python
VarMaxLength = int(dfName['ColumnName'].str.encode(encoding='utf-8').str.len().max())
print(VarMaxLength)
```

To see how many instances of a character (eg that you may want to replace) there are in a column (eg &)

```python
badchar = dfName['Column'].str.contains('\&', regex=True)
sum(badchar)
```

To count instances of each datapoint in a column

```python
dfName['Column'].value_counts()
```

To see all unique values in a column

```python
dfName.Column.unique()
```

## For manipulating dataframes

To rename columns

```python
dfName.rename(columns={'OldCol1':'NewCol1', 'OldCol2':'NewCol2'}, inplace=True)
```

To replace pesky problem characters

```python
dfName['Column'] = dfName['Column'].str.replace({'<old>': '<new>'}, regex=True)
#note: column name is optional

# handy replaces:

("'", '"') # single quotes to double quotes
('"', "'") # double quotes to single quotes
{r'\r': ' '} # replace carriage return chars with space
```

To change values depending on old value

```python
df['Column'] [df['Column'] == oldval] = newval
```

Trimming whitespace

```python

```
