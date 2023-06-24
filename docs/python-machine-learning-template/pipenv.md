## 🤔 Why Pipenv Over Pip and requirements.txt? 

If you've been using pip for your Python package installations 📦 and requirements.txt 📜 for package dependency creation, you might have encountered the following issues:

1. **Dependency Mismatch** 🧩: When sharing or deploying your project in different environments (like QA or Production), you typically share the requirements.txt file. However, if your project has been in development for a long time, there's a good chance that package installation may fail ❌ on the new machine due to dependency mismatches. This can lead to wasted time troubleshooting 🔧🔍 and resolving these issues.

2. **Long Proxy URL** 🌐: When working behind a proxy, you have to manually enter a long URL every time you want to install a Python package. This can be quite frustrating 😤 and time-consuming ⏰.

To address these challenges, we recommend using Pipenv 🎁. Pipenv maintains two files:

- **Pipfile** 📄: This is a human-readable dependency file for both base and development packages. It's easy to understand and manage.
- **Pipfile.lock** 🔒: This file stores the hashes of all packages and automatically resolves all dependencies. This ensures consistent installations across different environments.

### Advantages of using Pipenv in more detail 🏆:

- ✅ Pipenv simplifies virtual environment management and package dependencies 📦. 
- ✅ It automatically creates isolated virtual environments for projects 🏝️.
- ✅ Pipenv performs automatic dependency resolution for installed packages 🔗.
- ✅ Pipenv locks dependencies to specific versions for reproducibility 🔐.
- ✅ It integrates seamlessly with existing Python tools like pip and PyPI 🤝.
- ✅ Pipenv provides built-in environment activation when entering project directories 🚪.
- ✅ It offers clear and readable output for easy troubleshooting 📖.
- ✅ Seamless integration with `.env`. Loads the `.env` variables during package installation 🔄.
- ✅ To simplify handling proxy url for every pip install, you can now utilize Pipenv. Pipenv automatically reads the environment variables and incorporates them into your project 🎉.
