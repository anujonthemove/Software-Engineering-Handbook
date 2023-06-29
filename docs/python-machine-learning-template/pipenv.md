# 📢 **Pipenv for Dependency Management**

If you have been using pip for your Python package installations 📦 and requirements.txt 📜 for package dependency creation, you might have encountered the following issues:

1. 🧩 **Dependency Mismatch:** When sharing or deploying your project in different environments (like QA or Production), you typically share the `requirements.txt` file. However, if your project has been in development for a long time, there's a good chance that package installation may fail ❌ on the new machine due to dependency mismatches. This can lead to a lot of time being wasted troubleshooting 🔧🔍 and resolving these issues.

2. 🌐 **Long Proxy URL:** When working behind a proxy, you may have to manually enter a long URL every time you want to install a Python package. This can be quite frustrating 😤 and time-consuming ⏰.

To address these challenges, we recommend using Pipenv 🎁. Pipenv introduces a more efficient approach to package management by maintaining two files:

- 📄 **Pipfile:** This human-readable file serves as a comprehensive dependency manifest for both base and development packages. It provides a clear and manageable overview of your project's dependencies.

- 🔒 **Pipfile.lock:** This file stores the cryptographic hashes of all packages, ensuring consistent installations across different environments. Pipenv automatically resolves dependencies based on the information in the lock file, eliminating the chances of dependency conflicts.

??? note "**Advantages of using Pipenv**"

    * ✅ Simplified virtual environment management and package dependencies.
    * ✅ Automatic dependency resolution for installed packages.
    * ✅ Dependency locking to ensure reproducibility.
    * ✅ Seamless integration with existing Python tools like pip and PyPI.
    * ✅ Built-in environment activation when entering project directories.
    * ✅ Clear and readable output for easy troubleshooting.
    * ✅ Seamless integration with .env for loading environment variables during package installation.
    * ✅ Simplified handling of proxy URLs through automatic incorporation of environment variables by Pipenv.


Check out [Pipenv official documentation](https://pipenv.pypa.io/en/latest/) for more details!

____

### 📦 **Installing from Custom Index or Self-Hosted Repository**

If you're using a custom index or a self-hosted repository for your Python packages, you can specify these sources in your Pipfile. Here's how you can do it:

```toml

[[source]]
url = "https://your-repo-name.com/"
verify_ssl = true
name = "jfrog"

[[source]]
url = "https://your-repo-name.com/"
verify_ssl = false
name = "cdswrepo"

```

In the above configuration:

* `url` is the URL of your custom index or self-hosted repository.

* `verify_ssl` is a boolean value that determines whether SSL verification is required for the repository. Set it to true if SSL verification is needed; otherwise, set it to false.

* `name` is a unique identifier for the source. You can choose any name that makes sense to you.

Replace `your-repo-name.com` with your actual repository URLs. Please ensure that you have the correct SSL verification setting for each repository. Incorrect configuration may lead to installation failures.