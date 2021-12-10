# Great Expectations

1. Tutorial as described [here](https://docs.greatexpectations.io/docs/tutorials/getting_started/initialize_a_data_context)





## Known issues

Great Expectations depends on `numpy` which has issues with certain Python versions. In order for me to make this work for Python 3.9 I had to set the Python requirements for this Poetry project as `python = ">3.9,<3.11"` inside the `pyproject.toml`. Additionally, I also had to install `pandas` seperately. Current versions for packages are:

- great-expectations@0.13.46
- numpy@1.21.4
- pandas@1.3.4
