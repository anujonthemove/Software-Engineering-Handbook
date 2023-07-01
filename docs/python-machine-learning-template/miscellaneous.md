# **Miscellaneous**


## 📚 **Creating Detailed Project Documentation with MkDocs and Material for MkDocs**

[**MkDocs**](https://www.mkdocs.org/) is a handy tool that lets you create project documentation using Markdown. It's easy to use and quickly generates a static site for your documentation. The result is a professional, searchable, and customizable site, making it a great choice for projects of all sizes.

To make your MkDocs experience even better, you can use [**Material for MkDocs**](https://squidfunk.github.io/mkdocs-material/). This add-on provides a clean, responsive theme for your MkDocs-generated site. It supports over 60 languages and works perfectly on all devices. With Material for MkDocs, your project documentation can look more professional and be easier to use.

To start using these tools, you can check out their official documentation. Remember, code that is well-documented is easier to maintain, understand, and use, so these tools are really important for your project.

Together, these tools can help you create detailed project documentation, just like this Software Engineering guide you're reading now. 🤩

MkDocs needs you to keep the following structure:

```markdown

├── docs
│   └── index.md
└── mkdocs.yml

```

In this structure, all the markdown files are kept in the docs folder, and all the configuration is done in the mkdocs.yml file. The MkDocs python package is installed as part of the development packages, and to make it easy to use, we've already included the above structure in this template.

The installation of the Mkdocs-material theme package is up to you. It can be installed with the following command:

```shell
pipenv install mkdocs-material

```

____

## 📜 **Auto-Generating API Documentation with Pdoc3**

[**Pdoc3**](https://pdoc3.github.io/pdoc/) is a handy Python library that simplifies the process of generating API documentation for your Python projects. It operates by extracting docstrings from your public modules and objects, a functionality similar to tools like sphinx-apidoc or sphinx.ext.autodoc. However, Pdoc3 stands out due to its less complex and more lightweight design, making it an ideal choice for small to medium-sized projects.

One of the key features of Pdoc3 is its support for Markdown. This is a big plus for many developers who find Markdown more intuitive and user-friendly than reStructuredText (reST). By using Pdoc3, you can ensure that your code is well-documented and easy to understand, which encourages others to use and contribute to your project.

Pdoc3 generates attractive HTML documentation for all your codes. By default, these documents are stored in a folder named `html`, which is already included as part of this template. The Pdoc3 Python package is also installed along with other development packages when you set up your project using our setup scripts. We've got you covered 😎


____

## 📁 **Preserving Directory Structure with `.gitkeep`**

Git doesn't track empty directories. This can pose a challenge when you want to keep a specific directory structure in your project, even if some directories don't contain any files. The `.gitkeep` file is a workaround for this.

The `.gitkeep` file isn't an official Git feature. It's a convention that the community has adopted. Git will track directories that contain at least one file. By adding a `.gitkeep` file to an otherwise empty directory, you can ensure that Git tracks it.

In this project template, we've used `.gitkeep` files to push empty folders to the Git repository. This preserves the directory structure of the template when you clone or download it.

The name "`.gitkeep`" isn't special. You could use any filename to get Git to track an empty directory. The community uses "`.gitkeep`" because it's self-explanatory – anyone looking at the repository will understand its purpose. 🤓

____

## 🎫 **Adopting the [Cookiecutter](https://drivendata.github.io/cookiecutter-data-science/#directory-structure) Naming Convention for Jupyter Notebooks**


Machine Learning projects typically commence with exploratory data analysis. Jupyter Notebook is an invaluable tool for this phase, thanks to its seamless integration with libraries such as matplotlib, seaborn, plotly, bokeh, and pandas. These libraries enhance the visual output on Notebooks, making them an essential part of the entire Machine Learning project life cycle.

However, without a consistent naming convention, managing these notebooks can become a daunting task. It's not uncommon to find notebooks left unnamed, resulting in files like `Untitled.ipynb` or `Untitled1.ipynb`. Given the typically lengthy nature of Machine Learning code, it can be challenging to identify the final version of the code.

While designing this template, we discovered a naming convention in Cookiecutter templates and were instantly impressed. We have personally implemented this convention in numerous projects to maintain organization. We strongly encourage users of this template to adopt this convention if they don't already have one in place. It has proven to be highly effective. 

Here is the convention, directly taken from Cookiecutter:

Naming convention is a number (for ordering), the creator's initials, and a short `-` delimited description, e.g. `1.0-jqp-initial-data-exploration`. i.e., it follows a format of `<number>-<initials>-<short-description>`, e.g., `1.0-jqp-initial-data-exploration.ipynb`
