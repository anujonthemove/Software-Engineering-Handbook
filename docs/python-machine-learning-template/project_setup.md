<!-- # 🚀 **Platform-Specific Setup Scripts**

* 🔧 **Ready-to-Use Scripts for All Platforms:** Project setup scripts have been provided for all Linux, MacOS, and Windows which helps in setting up identical virtual environment across all of the platoforms.

* 📦 **Package Installation:** We use Pipfile(an alternate of requirements.txt), a human readable format,  to define a set of essentail packages for Machine Learning and Software Development tasks. These packages are installed using Pipenv(a better alternate of pip) to install these pacakges during the setup. To know how to utilize Pipenv, You may want to check out [Pipenv](pipenv.md) for more details.

* 🌐 **Seamless Proxy Support:** Install packages, even when behind a proxy, ensuring smooth integration with your development environment and eliminating any connectivity obstacles. Check out our documentation about how it works on [Pipenv](pipenv.md)

* 🗑️ **Automated Readme Cleanup:** The setup script can help you clear the template Readme.MD file after project setup. Just pass the required arguments to the script. More details about the usage below.

* 💡 **Virtual Environment Activation:** Upon successful execution of the setup script, a virtual environment named .venv will be activated automatically in your terminal. -->


# 🚀 **Platform-Specific Setup Scripts**

- 🚦 **Ready-to-Use Scripts for All Platforms:** We have prepared setup scripts for Linux, MacOS, and Windows platforms to ensure that the virtual environment is set up consistently across all platforms. These scripts will save you time and effort in setting up your project.

- 📦 **Package Installation:** To simplify package installation and maintainence, we use pipenv instead of pip. For more details, please refer to the [Pipenv documentation](pipenv.md).

- 🌐 **Proxy Support:** If you work behind a proxy, you may need to configure your proxy url in the `.env` file that gets generated once you run the setup scripts and pass the relevant argument to the setup script to enable pacakge installation. For more details, check out our documentation on working with [.env](dot-env.md)

- 🗑️ **Readme Cleanup:** Utilize relevant argument in the setup script to automatically clear the content of template Readme.MD file. More detailed instructions on usage below.

- 💡 **Virtual Environment:** Upon successful execution of the setup script, your terminal will automatically activate a virtual environment named `.venv`.

____


## **Setup script usage**

#### For Linux/MacOS

```shell
source project_setup.sh [OPTIONS] 
```

#### For Windows OS

```shell
project_setup.bat [OPTIONS]
```

Replace **[OPTIONS]** with any combination of the following supported arguments:

* `--install`: **Required argument**. If nothing is passed, a help message is displayed by default.

* `--install-dev`: Use this flag along with `--install` flag to install development packages.

* `--use-proxy`: Use this flag to enable installation of python packages behind proxy.

* `--unset-proxy`: Use this flag to disable proxy.

* `--clear-readme`: Use this flag to clear the contents of `README.md` file after setting up the project.
    * 📣 ***Caution: This should be used only once when you are setting up the project for the first time.***

* `--remove-cache`: Use this flag to remove `pip` and `pipenv` cache files.
    * 💡 ***Use this to clear cache files generated during package installation***

* `--help`: Use this flag to display the help message.


____


## **Detailed steps**

=== "🐧  Linux / 🍎 MacOS"

    For setting up the project on these platforms, `project_setup.sh` script has been provided along with some options. Check [Setup script usage](#setup-script-usage) section for details.

    #### 🧑‍💻 Steps for Linux/MacOS:

    1. Open terminal and navigate to your project directory.

        === "**Case (a): 🔰 Setting up in _Development_ environment**"
            * If you are setting up the project inside **development** environment, use:

                ```shell
                source project_setup.sh --install --install-dev
                ```

                * Incase you are working behind a proxy, use the following command instead:
                    
                    ```shell
                    source project_setup.sh --install --install-dev --use-proxy
                    ```

            * If you are setting up the project first time using this template, then you should replace contents of the README.md with the name of your project:

                ```
                source project_setup.sh --clear-readme
                ``` 
        
                ⚠️  *** Use this command only once in the development environment. DO NOT run this once you write your own readme. ***

        
        
        
        === "**Case (b): 🏁 Setting up in _Production_ environment**"

            * If you are setting up the project inside **production** environment, you may only require base packages, use:

                ```shell
                source project_setup.sh --install
                ```

                * Incase you are working behind a proxy, use the following command instead:
                
                    ```shell

                    source project_setup.sh --install --use-proxy
                    
                    ```

        !!! note "Important Note" 

            * ⛽ If want to install any other package inside this newly created virtual environment, please use the following command:

                ```
                pipenv install package_name
                ```

            * ❎ If you have configured proxy details in the `.env` file but later on you are not working behind proxy, you'd get package installation error as by default, `pipenv` loads all the `.env` variables, therefore you need to unset the proxy first.

                **Use the following command:**

                ```
                source project_setup.sh --unset-proxy
                ```

                You should then be able to install packages using pipenv as stated above.

            * ♻️ During package installation, the packages are downloaded and cached. This consumes a lot of disk, hence you should clear pip and pipenv cache from time to time. 
                
                **Use the following command:**

                ```
                source project_setup.sh --remove-cache
                ``` 
                This would remove all the cached files during package installation.

            *  ✅ To ensure a conflict-free environment setup, it is strongly recommended to always run the `project_setup.sh` script to create a virtual environment for your project.


            *  ❗You should run the script **ONLY** using the `source` command to ensure that the virtual environment `.venv` is automatically activated at the end of setup in the current shell session.

            * ⛔ Ideally, you should see a `.venv ` virtual environment already activated in the terminal. However, if it's not activated, please follow these steps to activate it before installing any package using pipenv:

                1. Open terminal.

                2. Navigate to the project directory.
                
                3. Activate the virtual environment by running the following command: `source .venv/bin/activate`. This command will activate the virtual environment and change your prompt to indicate that you're now working within it.

                4. You can now proceed with installing packages using `pipenv`
                    

=== "🪟 Windows"

    For setting up the project on Windows, `project_setup.bat` script has been provided along with some options.


    #### 🧑‍💻 Steps for Windows:

    1. Open Command Prompt (CMD) and navigate to your project directory.

        === "**Case (a): 🔰 Setting up in _Development_ environment** "

            * If you are setting up the project inside **development** environment, use:

                ```shell
                project_setup.bat --install --install-dev
                ```

                * Incase you are working behind a proxy, use the following command instead:
                        
                    ```shell
                    project_setup.bat --install --install-dev --use-proxy
                    ```

            * If you are setting up the project first time using this template, then you should replace contents of the README.md with the name of your project:

                ```
                project_setup.bat --clear-readme
                ``` 
            
                ⚠️ ***Use this command only once in the development environment. DO NOT run this once you write your own readme.***



        === " **Case (b): 🏁 Setting up in _Production_ environment**, "

    
            * If you are setting up the project inside **production** environment, you may only require base packages to be installaed, use:

                ```shell
                project_setup.bat --install
                ```

                * Incase you are working behind a proxy, use the following command instead:
                
                    ```shell
                    project_setup.bat --install --use-proxy
                    ```


        !!! note "Important Note" 

            * ⛽ If want to install any other package inside this newly created virtual environment, please use the following command:

                ```
                pipenv install package_name
                ```

            * ❎ If you have configured proxy details in the `.env` file but later on you are not working behind proxy, you'd get package installation error as by default, `pipenv` loads all the `.env` variables, therefore you need to unset the proxy first.

                **Use the following command:**

                ```
                project_setup.bat --unset-proxy
                ```

                You should then be able to install packages using pipenv as stated above.

            * ♻️ During package installation, the packages are downloaded and cached. This consumes a lot of disk, hence you should clear pip and pipenv cache from time to time. 
                
                **Use the following command:**

                ```
                project_setup.bat --remove-cache
                ``` 
                This would remove all the cached files during package installation.

            *  ✅ To ensure a conflict-free environment setup, it is strongly recommended to always run the `project_setup.bat` script to create a virtual environment for your project.


            *  ❗For security reasons, organizations may prevent running .bat scripts on PowerShell. You should run the script **ONLY** on Command Prompt (CMD) to ensure that everything runs without any errors.

            *  ⛔ Ideally, you should see a `.venv` virtual environment already activated in the Command Prompt (CMD). However, if it's not activated, please follow these steps to activate it before installing any package using `pipenv`:

                1. Open the Command Prompt (CMD).
                2. Navigate to the project directory.
                3. Activate the virtual environment by running the following command: `.venv\Scripts\Activate`. This command will activate the virtual environment and change your prompt to indicate that you're now working within it.

                4. You can now proceed with installing packages using `pipenv`


____


## 🎥 **Demo**

* 🌄 This demo assumes that you've cloned the project which you created using the Python Machine Learning Template on your machine. For the purposes of this demonstration, we'll refer to this project as `Demo Project`.

* 🏃 The video tutorial will guide you through the necessary steps for setting up your project. 

    <script async id="asciicast-aLntFu3A4w0JWivMfXLzfVvCv" src="https://asciinema.org/a/aLntFu3A4w0JWivMfXLzfVvCv.js"></script>


