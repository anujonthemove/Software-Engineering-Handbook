# Software Engineering Handbook


🚧 Under construction🚧

* Putting tried and tested things one by one here for the larger audience.



<details>

<summary> <b> 1. 🤔 Does this work with Anaconda distribution of Python? </b> </summary>

*  We did not intend to build this for Anaconda, it may work.

</details>



<details>
<summary> <b> 3. 🤔 What is the use of `.gitattributes`? </b> </summary>

*	The `.gitattributes` file is a standard Git configuration file. It allows you to specify attributes and behaviors for certain files in your repository. For example, you can define the line-ending style, binary or text attributes, and more.


</details>












   



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
