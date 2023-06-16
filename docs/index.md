# The Template Project

1. Minimal Python Project Template
2. Python Machine Learning Project Template
3. FastAPI Template



## 🎙️FAQs


<details>

<summary> <b> 1. 🤔 Does this work with Anaconda distribution of Python? </b> </summary>

*  We did not intend to build this for Anaconda, it may work.

</details>

<details>
<summary> <b> 2. 🤔 What is the use of `workspace` folder? </b> </summary>

*	The `workspaces` folder is intended for scenarios where multiple people are working on the same project on the same machine. Inside the `workspaces` folder, you can create subfolders named after each developer, allowing them to clone the project and work on different branches. These subdirectories are not tracked by Git, enabling multiple people to collaborate on the same project without conflicts. To incorporate changes, developers can merge their branches with a common branch located at the root level.

</details>

<details>
<summary> <b> 3. 🤔 What is the use of `.gitattributes`? </b> </summary>

*	The `.gitattributes` file is a standard Git configuration file. It allows you to specify attributes and behaviors for certain files in your repository. For example, you can define the line-ending style, binary or text attributes, and more.


</details>


<details>
<summary> <b> 4. 🤔 Is it inspired from cookie-cutter project template? </b> </summary>

*	In short, no. While there may be similarities in naming conventions, the Python Machine Learning Template was created based on the specific needs of machine learning projects, such as reinforcement learning, computer vision, and natural language processing. However, we do appreciate the Jupyter Notebook naming convention used in the cookie-cutter project template and we recommend that users should follow it.

	*	Here it is:

		*Naming convention is a number (for ordering), the creator's initials, and a short `-` delimited description, e.g. `1.0-jqp-initial-data-exploration`.* i.e., it follows a format of `<number>-<initials>-<short-description>`, e.g., `1.0-jqp-initial-data-exploration.ipynb`

</details>



<details>
<summary> <b> 5. 🤔 What is pipenv and why should we use it? </b> </summary>

* ✅ <a href="https://pipenv.pypa.io/en/latest/"> Pipenv </a> simplifies virtual environment management and package dependencies.
* ✅ It automatically creates isolated virtual environments for projects.
* ✅ Pipenv performs automatic dependency resolution for installed packages.
* ✅ It combines package installation, virtual environment activation, and dependency management.
* ✅ Pipenv locks dependencies to specific versions for reproducibility.
* ✅ It integrates seamlessly with existing Python tools like pip and PyPI.
* ✅ Pipenv provides built-in environment activation when entering project directories.
* ✅ It offers clear and readable output for easy troubleshooting.


</details>



<details>
<summary> <b> 6. 🤔 How can I make my supporting code in helpers folder accessible to my main/entrypoint code in the src folder since they both are at the same level? </b> </summary>

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

Now, you can place your main/entrypoint code in the 'src' folder and keep your supporting code in the 'helper' directory. Your project is ready to use this clean and organized structure.



</details>


*  ✅ If you have installed Python virtual environment and virtual environment wrapper and have set up a centralized location for virtual environments, you may have added the following to your `.bashrc` or `.zshrc` file:

      ```
      # virtualenv and virtualenvwrapper
      export WORKON_HOME=$HOME/.virtualenvs
      export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
      source /usr/local/bin/virtualenvwrapper.sh
      ```


   *  ⛔ Ideally, you should see a `.venv` virtual environment already activated in the Command Prompt (CMD). However, if it's not activated, please follow these steps to activate it before installing any package using `pipenv`:

      1. Open the Command Prompt (CMD).
      2. Navigate to the project directory.
      3. Activate the virtual environment by running the following command:

         `.venv\Scripts\Activate`

         This command will activate the virtual environment and change your prompt to indicate that you're now working within it.

      4. You can now proceed with installing packages using `pipenv` or running other commands within the activated virtual environment.

   * For Windows users, it's important to note that proxy settings made through editing the environment variables `$HTTP_PROXY` and `$HTTPS_PROXY` require elevated permissions.

   * To simplify handling proxy url for every pip install, you can now utilize `Pipenv`. Pipenv automatically reads the environment variables and incorporates them into your project.


1. prerequ installations and steps
2. vs code plugins and settings to enable
3. video steps
4. vs code settings and video
5. detailed usage of pipenv
6. proxy related pipenv
7. activating venv
8. how to use pipenv
9. using workspace folder - video
10. pep8 standards and how to enable/disable using tox
11. external index like jfrog


presentation using slidev?
check mkdocs to structure the above


*  ⛔ Ideally, you should see a `.venv` virtual environment already activated in the Command Prompt (CMD). However, if it's not activated, please follow these steps to activate it before installing any package using `pipenv`:

   1. Open the Command Prompt (CMD).
   2. Navigate to the project directory.
   3. Activate the virtual environment by running the following command:

      `.venv\Scripts\Activate`

      This command will activate the virtual environment and change your prompt to indicate that you're now working within it.

   4. You can now proceed with installing packages using `pipenv` or running other commands within the activated virtual environment.

* For Windows users, it's important to note that proxy settings made through editing the environment variables `$HTTP_PROXY` and `$HTTPS_PROXY` require elevated permissions.

* To simplify handling proxy url for every pip install, you can now utilize `Pipenv`. Pipenv automatically reads the environment variables and incorporates them into your project.
