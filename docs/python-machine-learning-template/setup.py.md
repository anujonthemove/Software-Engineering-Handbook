# 📦 **Packaging your Project with setup.py**

While working with a project structure where supporting code resides in folders at the same level as the `src` folder, you may encounter difficulties importing sub-modules from the `helpers` folder into the main/entrypoint code in the `src` folder. This issue can be resolved by utilizing `setup.py` in your project.

#### Here's a step-by-step guide to achieving this:

1. 📂 Open the `setup.py` file provided in your project. This file is crucial as it defines your project's configuration.


    ```python

    from setuptools import find_packages, setup

    setup(
        name="YOUR-PROJECT-NAME",
        version="1.0",
        packages=find_packages(),
    )

    ```

2. ✏️ Update the `name` variable in `setup.py` to match the ***root folder name*** of your project. This step ensures your project is properly identified.

3. 🖥️ Open the terminal or Command Prompt (CMD) and navigate to the project directory. Ensure you are in the root folder of your project and your project's virtual environment is active.

    !!! note
        *   🤔 If you have doubts regarding virtual environment activation, refer to the [project setup](project-setup.md) section for detailed instructions tailored to your specific operating system.

        *   😎 An `__init__.py` file is already present in the helpers folder. The presence of this file allows the helpers folder to function as a module that can be accessed from anywhere within the package.

4. ▶️ Run the following command in your terminal or CMD: 

    * If you are on Linux, you should use the following command to install your project as a package:

        ```shell
            pipenv install -e .
        ```

    CHECK ON MAC AND WINDOWS AND COME BACK
    
    * If you are on MacOS, you mighty have to use the following command to install your project as a package:

        ```shell

        python setup.py install

        ```
        or

        ```shell
        python setup.py .

        ```

    !!! note
        *   ✅ Ensure you include the . at the end of the command. This command installs your project as a package, granting it importability and enabling you to organize your code in a modular and convenient manner.

        *   🆗 This should automatically add your project as a package to your current virtual environment. You can verify the same in your `Pipfile`. You should see the following line:
        
            `your-project-name = {editable = true, path = "."}`


        
    
??? danger "About setup.py"
    💡 The `setup.py` file is not limited to these functionalities. It is a much more powerful tool that can be leveraged for various other tasks.