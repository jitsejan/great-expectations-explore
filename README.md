# Great Expectations

1. Tutorial as described [here](https://docs.greatexpectations.io/docs/tutorials/getting_started/initialize_a_data_context)





## Known issues

Great Expectations depends on `numpy` which has issues with certain Python versions. In order for me to make this work for Python 3.9 I had to set the Python requirements for this Poetry project as `python = ">3.9,<3.11"` inside the `pyproject.toml`. Additionally, I also had to install `pandas` seperately. Current versions for packages are:

- great-expectations@0.13.46
- numpy@1.21.4
- pandas@1.3.4


The next issue was opening a Jupyter notebook to add a new data source. The `mistune` packages was throwing an error that it doesn't have the `BlockGrammar` attribute. Downgrading from `2.0.0.` to `0.8.4` resolved this.


On MacOSX with M1 I had issues with importing `pandas`.

```
>>> import pandas
/Users/jitsejan/Library/Caches/pypoetry/virtualenvs/great-expectations-explore-cv0VYAwJ-py3.9/lib/python3.9/site-packages/pandas/compat/__init__.py:124: UserWarning: Could not import the lzma module. Your installed Python is incomplete. Attempting to use lzma compression will result in a RuntimeError.
  warnings.warn(msg)
```

In order to fix this I had to install the Python version with `xz` as install flag.

```
$ CPPFLAGS="-I$(brew --prefix xz)/include" pyenv install 3.9.7
```
