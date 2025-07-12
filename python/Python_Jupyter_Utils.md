## A list of useful functions by Mahboob Alam

* To adjust jupyter window size
```python
def fit_window(arg=0):
    from IPython.display import display, HTML
    if arg<=0:
        arg=100
    elif arg<=65:
        arg = 65
    else:
        arg =arg
        
    htmlstr = "<style>.container { width:" + str(arg) +"% !important; }</style>"
    display(HTML(htmlstr))
```

* To Merge multiple pandas dataframes

```python
def merge_dfs(dfs, on, how='inner'):
    return reduce(lambda left,right: pd.merge(left, right, on=on, how=how), dfs)
```
* A custom header based on pretty print 
```python
def head(df, n=5, msg='data frame'):
    rprint(f"[green bold]{msg}[/green bold]", end="")
    rprint(df.head(n))
```

* To display table side_by_side
```python
def table_side_by_side(dfs, names=[], n=10):
    df_styler_str = ''
    for i, df in enumerate(dfs):
        df = df.head(n)
        tmp_styler = df.style.set_table_attributes(
            "style='display:inline'").set_caption(f'{names[i]}')
        df_styler_str += tmp_styler._repr_html_()

    display_html(df_styler_str, raw=True)
    # display_html(df1_styler._repr_html_() + df2_styler._repr_html_(), raw=True)
```

* To open a target directory
```python
def goto_dir(dirpath):
    os.startfile(dirpath, 'open')
```

* To open a targte file
```python
def view_file(filepath, editor_path="notepad.exe"):
    subprocess.Popen([editor_path, filepath])
```
* To copy a file
```python
def copy_file(filename, destination):
    shutil.copy(filename, destination)
```

* To convert a unix line-ending to windows line-ending
```python
def unix2dos(filename):
    f = open(filename, 'r')
    fo = open(filename+'.dos', 'w')
    for i in f:
        print(i.rstrip(), file=fo)
    fo.close()
    f.close()
    return fo.name
```

* To draw a table border in Jupyter Notebook
```python
def table_border(show=False):
    if show:
        display(
            HTML("<style> table, td, tr, th {border: 1pt solid!important} </style>"))
    else:
        display(
            HTML("<style> table, td, tr, th {border: none!important} </style>"))
```

* To find all duplicates in pandas df
```python
def show_all_duplicates(df, var_list):
    """to show all duplicates"""
    #
    def reduce_join(df, columns):
        assert len(columns) > 1
        slist = [df[x].astype(str) for x in columns]
        return reduce(lambda x, y: x + '_' + y, slist[1:], slist[0])
    #
    ids = reduce_join(df, var_list)
    df = df[ids.isin(ids[ids.duplicated()])].sort_values(by=var_list)
    return df
```

* To get the target variable from python environment
```python
def get_var(df, var_name):
    globals()[var_name] = df
    return df
```
* To save a file into a fixed-width-format. A sample code.
```python
def save_fwf(filename, df):
    with open(filename, 'w') as ofile:
        #      'a    s    d   yr  aebv   sebv   debv   arel  srel  drel '
        fmt = '%12s %12s %12s %4s %10.3f %10.3f %10.3f %7.3f %7.3f %7.3f'
        np.savetxt(ofile, df.values, fmt=fmt)
```        

* To read a parquet or pickle from disk
```python
def read_parquet_pickle(path_prefix, ftype='parquet', columns=[]):
    if ftype == 'parquet':
        if columns:
            df = pd.read_parquet(f"{path_prefix}.{ftype}", columns=columns)
        else:
            df = pd.read_parquet(f"{path_prefix}.{ftype}")
        return df
    else:
        df = pd.read_pickel(f"{path_prefix}.{ftype}")
        # pd.read_pickle(f'{out_path}/pedigree/dam.pickle')
        return df
```


* To write a parquet or a pickle to the disk
```python
def write_parquet_pickle(df, df_str, out_path, ftype='parquet', columns=[]):
    if ftype == 'parquet':
        if columns:
            df[columns].to_parquet(f'{out_path}/{df_str}.parquet')
        else:
            df.to_parquet(f'{out_path}/{df_str}.{ftype}')
    else:
        pd.to_pickle(f'{out_path}/{df_str}.{ftype}')
```

* watchdog
```python
from watchdog.observers import Observer
from watchdog.events import FileSystemEventHandler
```
