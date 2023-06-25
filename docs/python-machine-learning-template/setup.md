

## 🚀 Platform-Specific Setup Scripts

* 🔧 **Ready-to-Use Scripts for All Platforms:** Simplify the project setup process with provided scripts tailored for Linux, MacOS, and Windows, ensuring compatibility across different operating systems.

* 📦 **Effortless Package Installation:** Install a curated list of Python packages defined in the Pipfile, designed specifically for Machine Learning and Software Development tasks, saving you time and effort.

* 🌐 Seamless Proxy Support: Install packages effortlessly, even when behind a proxy, ensuring smooth integration with your development environment and eliminating any connectivity obstacles.

* 🗑️ **Automated Readme Cleanup:** Say goodbye to clutter! The setup script intelligently clears unnecessary information from the template Readme.MD file after project setup. Just pass the required arguments, and enjoy a clean and concise README.

* 💡 **Virtual Environment Activation:** Get started quickly! Upon successful execution of the setup script, a virtual environment named .venv will be activated automatically in your terminal.

____


## Command options

```shell
## For Linux/MacOS
source project_setup.sh [OPTIONS] 
```

or

```shell

## For Windows OS
project_setup.bat [OPTIONS]

```

Replace [OPTIONS] with any combination of the following options:

* `--install`: **Required argument**. If nothing is passed, a help message is displayed.

* `--install-dev`: Optional argument. Pass this flag along with `--install` flag to install development packages.

* `--use-proxy`: Optional argument. This flag enables installation of python packages behind proxy. Check Using .env section for proxy configuration.

* `--unset-proxy`: Optional argument. This flag disables proxy.

* `--clear-readme`: Optional argument. Clear README.md file after setting up the project.
    * 📣 ***Caution: Use this only when you are setting up the project for the first time.***

* `--remove-cache`: Optional argument. Removes `pip` and `pipenv` cache files.
    * 💡 ***Use this to clear cache files generated during package installation***

* `--help`: Display the help message.


____



## 🎥 Demo

This demo assumes that you've already set up your own project using the Python Machine Learning Template. For the purposes of this demonstration, we'll refer to this project as `Demo Project`.

The video tutorial will guide you through the necessary steps for setting up your project. Please note that the video does not include the process of clearing the readme at the end of the setup.

For more detailed instructions and additional information, please refer to the documentation provided below. This will give you a comprehensive understanding of the setup process and how to clear the readme.


<script async id="asciicast-aLntFu3A4w0JWivMfXLzfVvCv" src="https://asciinema.org/a/aLntFu3A4w0JWivMfXLzfVvCv.js"></script>

____

## Command usage

=== "🐧  Linux / 🍎 MacOS"

    For setting up the project, `project_setup.sh` script has been provided along with some options.



    ### 🧑‍💻 Steps:

    1. Open terminal and navigate to your project directory.

        **Case (a): Setting up in _Development_ environment** 
        
        If you are setting up the project inside **development** environment, use:

        ```shell
        source project_setup.sh --install --install-dev
        ```

        Incase you are working behind a proxy, use the following command instead:
            
        ```shell
        source project_setup.sh --install --install-dev --use-proxy
        ```
        

        **Case (b): If you are setting up the project in _production_ environment**, 
        
        If you are setting up the project inside **production** environment, you may only require base packages to be installaed, use:

        ```shell
        source project_setup.sh --install
        ```

        If you are working behind a proxy, use the following command:
        
        ```shell

        source project_setup.sh --install --use-proxy
        
        ```

    2. If you are setting up the project first time using this template, then you should replace contents of the README.md with the name of your project:

        ```
        source project_setup.sh --clear-readme
        ``` 
    
        ***Use this command only once in the development environment. DO NOT run this once you write your own readme. Also, do not run this in production environment.***



    #### 📝 Important Note 

    *  For any other package installation apart from the listed packages in `Pipfile` use `pipenv` as follows:

        ```
        pipenv install package_name
        ```

        By default, `pipenv` loads all the `.env` variables, therefore you need to unset the proxy first if you are not behind proxy.

        Use the following command:

        ```
        source project_setup.sh --unset-proxy
        ```
        You should then be able to install packages using pipenv as stated above.

    *  During package installation, the packages are downloaded and cached. This consumes a lot of disk, hence you should clear pip and pipenv cache from time to time. Use the following command:

        ```
        source project_setup.sh --remove-cache
        ``` 


    *  ✅ To ensure a conflict-free environment setup, it is strongly recommended to always run the `project_setup.sh` script to create a virtual environment for your project.


    *  ❗You should run the script **ONLY** using the `source` command to ensure that the virtual environment `.venv` is automatically activated at the end of setup in the current shell session.

    *  🤚 If you have installed Python virtual environment and virtual environment wrapper and have set up a centralized location for virtual environments, you may have added the following to your `.bashrc` or `.zshrc` file:

        ```
        # virtualenv and virtualenvwrapper
        export WORKON_HOME=$HOME/.virtualenvs
        export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
        source /usr/local/bin/virtualenvwrapper.sh
        ```

    

=== "🪟 Windows"

    For setting up the project, `project_setup.bat` script has been provided along with some options.


    ### 🧑‍💻 Steps:

    1. Open Command Prompt (CMD) and navigate to your project directory.

        **Case (a): Setting up in _Development_ environment** 
    
        If you are setting up the project inside **development** environment, use:

        ```shell
        project_setup.bat --install --install-dev
        ```

        Incase you are working behind a proxy, use the following command instead:
                
        ```shell
        project_setup.bat --install --install-dev --use-proxy
        ```


        **Case (b): If you are setting up the project in _production_ environment**, 
    
        If you are setting up the project inside **production** environment, you may only require base packages to be installaed, use:

        ```shell
        project_setup.bat --install
        ```

        If you are working behind a proxy, use the following command:
        
        ```shell
        project_setup.bat --install --use-proxy
        ```

    2. If you are setting up the project first time using this template, then you should replace contents of the README.md with the name of your project:

        ```
        project_setup.bat --clear-readme
        ``` 
    
        ***Use this command only once in the development environment. DO NOT run this once you write your own readme. Also, do not run this in production environment.***



    #### 📝 Important Note 

    *  For any other package installation apart from the listed packages in `Pipfile` use `pipenv` as follows:

        ```
        pipenv install package_name
        ```

        By default, `pipenv` loads all the `.env` variables, therefore you need to unset the proxy first if you are not behind proxy.

        Use the following command:

        ```
        project_setup.bat --unset-proxy
        ```
        You should then be able to install packages using pipenv as stated above.

    *  During package installation, the packages are downloaded and cached. This consumes a lot of disk, hence you should clear pip and pipenv cache from time to time. Use the following command:

        ```
        project_setup.bat --remove-cache
        ``` 

    *  ✅ To ensure a conflict-free environment setup, it is strongly recommended to always run the `project_setup.bat` script to create a virtual environment for your project.

    *  ❗For security reasons, organizations may prevent running .bat scripts on PowerShell. You should run the script **ONLY** on Command Prompt (CMD) to ensure that everything runs without any errors.

    *  ⛔ Ideally, you should see a `.venv` virtual environment already activated in the Command Prompt (CMD). However, if it's not activated, please follow these steps to activate it before installing any package using `pipenv`:

        1. Open the Command Prompt (CMD).
        2. Navigate to the project directory.
        3. Activate the virtual environment by running the following command: `.venv\Scripts\Activate`

            This command will activate the virtual environment and change your prompt to indicate that you're now working within it.

        4. You can now proceed with installing packages using `pipenv`


