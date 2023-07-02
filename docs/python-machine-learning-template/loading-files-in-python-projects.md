# 📬 **Loading Configuration and Data Files in Python Projects**

This section provides instructions on how to load configuration files (such as `config.yml`) and data files (such as `amazon_alexa.tsv`) in Python projects. The instructions are applicable when the configuration files are located in a `config` directory and the data files are located in a `data` directory at the root level of the project. You may want to check the [setup.py](setup.py.md) section to understand the importance of this section.

**Your files could be structured as below:**

```markdown

.
├── config
│   ├── config.yml
│   ├── __init__.py
├── data
│   └── text
│       └── amazon_alexa.tsv
├── helpers
│   ├── helper.py
│   ├── __init__.py
├── notebooks
│   └── test_code.ipynb
├── setup.py
└── src
    └── test_code.py
```


## 🪝 **Loading Configuration Files**

### ⚔️ **Loading using `importlib.resources`**

Configuration files (like `config.yml`) can be loaded as a package resource using the `importlib.resources` module in Python. 

Here's a sample code snippet:

```py title="test_code.ipynb"

import yaml
import importlib.resources

def read_config():
    # Read the resource as text
    resource_string = importlib.resources.read_text('config', 'config.yml')
    
    # Load the yaml file
    config = yaml.safe_load(resource_string)
    
    return config

```

In this code, `'config'` is the name of the package where the `config.yml` file is located, and `'config.yml'` is the name of the resource. It should be a file in the `config` package.

To load the configuration file as a package resource, you need to include it in your `setup.py` file. Here's how you can do it:

```py title="setup.py"

from setuptools import find_packages, setup

setup(
    name="Test-Project", 
    version="1.0", 
    packages=find_packages(),
    
    # added these lines
    package_data={'': ['config/*.yml']},
    include_package_data=True,
)
```


In this code, `package_data={'': ['config/*.yml']}` tells setuptools to include all `.yml `files in the `config` directory in any package, and `include_package_data=True` tells `setuptools` to include any data files specified in `package_data`.

!!! danger "Caution"

    This way you are telling python that your `config.yml` should be treated as a part of the project package. When you run the code for the first time, in order to optimize loading for the second time, python will cache this file. Now, if you change some values in the `config.yml` file, and re-run the code, you might get the previous values that were set in the config.yml file. This is not what you intended to do but python does it inherently to save loading the next time. It is strictly adviced not to use this method for loading config files, you may use it for those files which are not expected to change much. Even re-running `pipenv install -e .` command did not overwrite the cached config.yml file. You should choose this method for files that suites your purpose.


### 🧲 **Loading as a Regular File**


Alternatively, you can load the configuration file as a regular file without including it as a package resource. 

Here's how you can do it:

```py title="test_code.ipynb"

import yaml
import os

def read_config():
    # Get the current working directory
    current_dir = os.getcwd()

    # Get the config file path
    config_file_path = os.path.join(current_dir, '..', 'config', 'config.yml')

    # Resolve the relative path to an absolute path
    config_file_path = os.path.abspath(config_file_path)

    # Load the yaml file
    with open(config_file_path, 'r') as file:
        config = yaml.safe_load(file)

    return config

```

In this code, `os.getcwd()` gets the current working directory, `os.path.join(current_dir, '..', 'config', 'config.yml')` constructs the path to the config file relative to the current working directory, `os.path.abspath(config_file_path)` resolves the relative path to an absolute path, and `yaml.safe_load(file)` loads the yaml file.

### 💣 **Loading with pkg_resources ([this will soon get deprecated](https://setuptools.pypa.io/en/latest/pkg_resources.html))**

You can also load the configuration file using `pkg_resources`, but please note that `pkg_resources` is being phased out in favor of `importlib.resources`. Here's how you can do it:


```py title="test_code.ipynb"

import pkg_resources
import yaml

def read_config():
    config_path = pkg_resources.resource_filename('config', 'config.yml')
    with open(config_path, 'r') as file:
        config = yaml.safe_load(file)
    return config


```

## 📈 **Loading Data Files**

Data files (like `amazon_alexa.tsv`) can be loaded using the pandas library in Python. Here's a sample code snippet:



```py title="test_code.ipynb"

import pandas as pd
import os

def read_data():
    # Get the current working directory    
    current_dir = os.getcwd()

    # Get the data file path
    data_file_path = os.path.join(current_dir, '..', 'data', 'text', 'amazon_alexa.tsv')

    # Resolve the relative path to an absolute path
    data_file_path = os.path.abspath(data_file_path)

    # Read the data file
    data = pd.read_csv(data_file_path, sep='\t')

    return data


```

In this code, `os.getcwd()` gets the current working directory, `os.path.join(current_dir, '..', 'data', 'text', 'amazon_alexa.tsv')` constructs the path to the data file relative to the current working directory, o`s.path.abspath(data_file_path)` resolves the relative path to an absolute path, and `pd.read_csv(data_file_path, sep='\t')` reads the data file into a pandas DataFrame.

Please replace `'..'`, `'data'`, `'text'`, and `'amazon_alexa.tsv'` with the actual relative path from your script or notebook to amazon_alexa.tsv if it's different in your project.


## 🧪 **Running Python Scripts from the Root of the Project**

### 🧭 **Loading config file**

When you run a Python script from the root of the project (for example, `python src/test_code.py`), the current working directory is the root of the project, not the directory where the script is located. In this case, you can use the `__file__` variable to get the directory of the script, and then construct the path to the configuration or data file relative to the script directory. Here's how you can do it:


```py title="test_code.py"

import yaml
import os

def read_config():
    # Get the directory of the script
    script_dir = os.path.dirname(os.path.abspath(__file__))

    # Get the config file path
    config_file_path = os.path.join(script_dir, '..', 'config', 'config.yml')

    # Load the yaml file
    with open(config_file_path, 'r') as file:
        config = yaml.safe_load(file)

    return config


```


In this code, `os.path.dirname(os.path.abspath(__file__))` gets the directory of the script, `os.path.join(script_dir, '..', 'config', 'config.yml')` constructs the path to the config file relative to the script directory, and `yaml.safe_load(file)` loads the yaml file.

### 🏗️ **Loading data files**


```py title="test_code.py"
import pandas as pd
import os

def read_data():
    # Get the directory of the script
    script_dir = os.path.dirname(os.path.abspath(__file__))

    # Get the data file path
    data_file_path = os.path.join(script_dir, '..', 'data', 'text', 'amazon_alexa.tsv')

    # Read the data file
    data = pd.read_csv(data_file_path, sep='\t')

    return data

```


In this code, `os.path.dirname(os.path.abspath(__file__))` gets the directory of the script, `os.path.join(script_dir, '..', 'data', 'text', 'amazon_alexa.tsv')` constructs the path to the data file relative to the script directory, and `pd.read_csv(data_file_path, sep='\t')` reads the data file into a pandas DataFrame.