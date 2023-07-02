# 📦 **Packaging your Project with setup.py**

When working with a project structure like this where supporting code resides in folders at the same level as the `src` or `notebooks` folder, you will not be able to import sub-modules from the `helpers` folder into the main/entrypoint code in the `src` folder even though it contains `__init__.py` file indicating that it can be used as a module.

For example, let us say you have a file named `helper.py` under `helpers` folder

```py title="helper.py"

import numpy as np

def test_numpy():
    print("Using Numpy")
    a = np.array([10, 20])
    print("Array: ", a)

```

and you are trying to use this `helper.py` in your code under the `src` folder

```py title="test_code.py"

from helpers import helper

helper.test_numpy()

```

When you run the code from the project root `python src/test_code.py`, you will be greeted with the following error:

```shell
Traceback (most recent call last):
  File "src/test_code.py", line 1, in <module>
    from helpers import helper
ModuleNotFoundError: No module named 'helpers'

```

<span style="color:red">This can be resolved by utilizing `setup.py` in your project.</span>

**Here's a step-by-step guide to achieving this:**

1. 📂 Open the `setup.py` file provided in the template. At very basic level, it looks like this:

    ```py title="setup.py"

    from setuptools import find_packages, setup

    setup(
        name="YOUR-PROJECT-NAME",
        version="1.0",
        packages=find_packages(),
    )

    ```

2. ✏️ Update the `name` variable in `setup.py` to match the ***root folder name*** of your project. This step ensures your project is properly identified.

3. 🖥️ Open the terminal or Command Prompt (CMD) and navigate to the project directory. Ensure you are in the root folder of your project and your project's virtual environment is active.

    ??? note
        *   🤔 If you have doubts regarding virtual environment activation, refer to the [**project setup**](project-setup.md) section for detailed instructions tailored to your specific operating system.

        *   😎 An `__init__.py` file is already present in the helpers folder. The presence of this file allows the helpers folder to function as a module that can be accessed from anywhere within the package.

4. ▶️ Run the following command in your terminal or CMD: 

    ```shell
        pipenv install -e .
    ```
    ??? note
        *   ✅ Ensure you include the `.` at the end of the command. This command installs your project as a package, granting it importability and enabling you to organize your code in a modular and convenient manner.

        *   🆗 This should automatically add your project as a package to your current virtual environment. You can verify the same in your `Pipfile`. You should see the following line:
        
            `your-project-name = {editable = true, path = "."}`


Once the opertion is complete, now when you try to run the code from the project root `python src/test_code.py`, it now will run successfully. 

For the above example, it will show you the following output:

```
Using Numpy
Array:  [10 20]
```
    
??? danger "About setup.py"
    💡 The `setup.py` file is not limited to this, it is a much more powerful tool that can be leveraged for various other tasks which is a bit out of scope to explain it here.