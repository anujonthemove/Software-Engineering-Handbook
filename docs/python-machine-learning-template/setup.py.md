<!-- When working with a project structure like this, I wanted to make my supporting code in helpers folder accessible to my main/entrypoint code in the src folder since they both are at the same level. For this, I found setup.py to be useful. 

To achieve this in a clean manner, you can structure your project as a package. Follow these steps:

1. Open the `setup.py` file provided in your project, which contains the following code:

```python
from setuptools import find_packages, setup

setup(
    name="<YOUR_PROJECT_NAME>",
    version="1.0",
    packages=find_packages(),
)

```

2. Update the value of the `name` variable to match the root folder name of your project.
3. Open the terminal or Command Prompt (CMD) and navigate to the project directory.
4. Ensure that your project's virtual environment is active. If not, refer to the **Setup** section in the README for instructions specific to your operating system.
5. Add a file named `__init__.py` to the `helper` folder. This file allows the `helper` folder to be used as a module from anywhere in the package.
6. Run the following command: `pip install -e .`. ⚠️ Do not forget the `.`

   This command installs your project as a package, making it importable and allows you to organize your code in a modular way.

Now, you can place your main/entrypoint code in the 'src' folder and keep your supporting code in the 'helper' directory. Your project is ready to use this clean and organized structure. -->

# 📦 **Packaging your Project with Setup.py** 

When working with a project structure like this, where you have supporting code in the `helpers` folder and main/entrypoint code in the `src` folder, it's essential to ensure accessibility and maintain a clean project organization. To achieve this, you can leverage the power of `setup.py` in your project.

Here's how you can accomplish this in an efficient manner:

1. 📂 Open the `setup.py` file provided in your project. This file plays a crucial role in defining your project's configuration.


    ```python

    from setuptools import find_packages, setup

    setup(
        name="<YOUR_PROJECT_NAME>",
        version="1.0",
        packages=find_packages(),
    )



    ```


2. ✏️ Update the value of the `name` variable in `setup.py` to match the root folder name of your project. This step ensures that your project is properly identified.

3. 🖥️ Open the terminal or Command Prompt (CMD) and navigate to the project directory. Make sure you are in the root folder of your project.

4. 🧪 Ensure that your project's virtual environment is active. If you haven't set up a virtual environment, refer to the Setup section for detailed instructions tailored to your specific operating system.

5. ➕ Add a file named __init__.py to the helper folder. The presence of this file allows the helper folder to function as a module that can be accessed from anywhere within the package.

6. ▶️ Run the following command in your terminal or CMD: `pipenv install -e .`. Ensure that you include the . at the end of the command.

    * If you are on MacOS, you should use the following command to install your project as a package:

        ```shell

        python setup.py install

        ```
        or

        ```shell
        python setup.py .

        ```

    This command installs your project as a package, granting it importability and enabling you to organize your code in a modular and convenient manner.








