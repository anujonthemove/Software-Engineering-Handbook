
## 🔑 Python, Virtual Environment, VS Code(Opt)

=== "🐧Linux"

    #### 🚀 Installing Python3 on Linux
    
    1. Open the Terminal application.

    2. Update your local package index and upgrade all your installed packages to their latest versions by running the following command:

        ```shell


        sudo apt update && sudo apt upgrade -y

        ```
    
    3. Install the necessary dependencies for Python3 by running the following command:

        ```shell
        sudo apt install software-properties-common build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev
        ```

    4. Add the deadsnakes PPA to your sources. This repository contains the latest versions of Python. Run the following command to add it:

        ```shell
        sudo add-apt-repository ppa:deadsnakes/ppa
        ```
    5. Update your local package index again to include the packages from the newly added repository by running the following command:

        ```shell
        sudo apt update
        ```

    6. Install Python3, pip (Python's package manager), and the virtual environment package by running the following command:
    
        ```shell
        sudo apt install python3 python3-pip python3-venv

        ```

    7. Check the installed version of Python3 by running the following command:
    
        ```shell
        python3 --version

        ```

    This should display the version of Python3 that you just installed.

    #### 🎨 Install VS Code

    1. Install Visual Studio Code via Snap. Snap is a software deployment and package management system developed by Canonical (the company behind Ubuntu). It allows you to install software and all its dependencies via a single command. Run the following command to install Visual Studio Code:

        ```shell
        sudo snap install --classic code
        ``` 

    2. Check that Visual Studio Code has been installed correctly by running the following command:

        ```shell

        code --version

        ```

    This should display the version of Visual Studio Code that you just installed.

    #### References: 

    1. Getting Started with Python in VS Code: https://code.visualstudio.com/docs/python/python-tutorial 
    2. Install Python on Ubuntu: https://www.makeuseof.com/install-python-ubuntu/

=== "🍎 MacOS"

    #### 🛰️ Installing Python3 on MacOS

    1. Open the Terminal application by pressing command + space, typing terminal, and hitting return.

    2. Check if Python 3 is installed on your Mac by typing the following command in the Terminal:

        ```shell
        
        python3 --version

        ```

        If Python 3 is not installed, a message will appear in the Terminal, and a dialog box will pop up saying this command requires the command line developer tools. Click on the Install button and follow the steps to complete the installation process.

    4. Once the installation process is complete, rerun the previous command. Python 3.x should now be installed on your Mac.

    Alternatively, you can install Python 3 using the Official Installer:

    1. Visit the [Python official website](https://www.python.org/downloads/) on your Mac. The website should automatically detect your operating system and show a big button for downloading the latest Python installer for your Mac. If it doesn't, click the macOS link and choose the latest Python release.

    2. Once the download is complete, double-click the package to start installing Python. The installer will guide you through the installation process. In most cases, the default settings work well. You may also need to enter your Mac password to authorize the installation.

    3. When the installation completes, it will open up the Python folder.

    4. Verify that the latest version of Python and IDLE installed correctly. To do this, double-click IDLE, which is the integrated development environment that comes with Python. If everything works correctly, IDLE will display the Python shell.


    #### 🎨 Install VS Code

    1. Download Visual Studio Code for MacOS from [VS Code official website](https://code.visualstudio.com/).

    2. Double-click the downloaded file to extract the archived contents.

    3. Move the Visual Studio Code application to the Applications folder to make it available in the MacOS Launchpad.

    4. Launch Visual Studio Code, then open a folder where your Python scripts are located (or create a new one). For example, create a new folder on your Desktop named "py_scripts", then try to open the folder in VS Code. VS Code may need your permission to access files in your Desktop folder; click OK if prompted.

    5. Create a new file with a .py extension. For example, create a new file named "prog_01.py". VS Code will detect the .py extension and suggest installing a Python extension. Install it by clicking on the Install button.

    6. Once the extension is installed, you need to select a Python interpreter. Click on the "Select Python Interpreter" button and then select the recommended Python interpreter from the list. If you have multiple versions of Python installed on your Mac, it's best to choose the latest version.

    You can now write and run Python code inside VS Code.


    #### References: 
    1. Getting Started with Python in VS Code: https://code.visualstudio.com/docs/python/python-tutorial 
    2. Python & VS Code installation steps on Mac: https://www.dataquest.io/blog/installing-python-on-mac/
    

=== "🪟 Windows"

    #### 🛸 Installing Python3 on Windows
    
    1. Download the latest Python distribution from the Official Python website. 

    2. Double-click on the file to run the installer.
        
    * In the installer, make sure you check the box that says "Add Python 3.7 to PATH" and then click on "Install Now". This will start the installation process.

    3. Once the installation is complete, you can verify the installation. To do this, open a new command prompt window. You can do this by pressing the Windows key, typing "cmd", and hitting Enter.

    4. In the command prompt window, type the following command:

        ```shell
        python --version

        ```

    #### 🎨 Install VS Code

    1. Download the Visual Studio Code installer for Windows.
    2. Once it is downloaded, run the installer (VSCodeUserSetup-{version}.exe). This will only take a minute.
    3. By default, VS Code is installed under `C:\Users\{Username}\AppData\Local\Programs\Microsoft VS Code`.

    Alternatively, you can also download a Zip archive, extract it and run Code from there.



**Note:** If you are using Python 3.3 or newer, the venv module is the preferred way to create and manage virtual environments. venv is included in the Python standard library and requires no additional installation.

