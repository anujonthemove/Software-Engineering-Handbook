# **🕹️ Managing File Attributes in Git Repository**


### 🙆 **Problem**

During the development of a large-scale project involving multiple developers across various platforms, we encountered a recurring issue. Developers were reporting an error when attempting to commit their code.

!!! danger "Error"

    ```
    git commit get fatal error "fatal: CRLF would be replaced by LF in..."
    ```


### 💁 **Solution**

The immediate solution was to instruct each developer to add the following configuration to their git config: 

```
'git config --global core.autocrlf false'. 
```

However, we sought a more proactive approach to prevent such an error from arising in the first place.
    
Our research led us to the use of `.gitattributes`, which we decided to incorporate into our template.


The `.gitattributes` file is a configuration file that allows you to specify attributes and behaviors for certain files in your repository. Define the line-ending style, binary or text attributes, and more.

**Part of the configuration we implemented is as follows:**

```markdown

# Normalize line endings to LF on check-in and prevent conversion to CRLF when checked out.
# This is necessary to prevent newline related issues, 
#  such as those that might occur after running the build script.

.*      text eol=lf
*.css   text eol=lf
*.html  text eol=lf
*.js    text eol=lf
*.json  text eol=lf
*.scss  text eol=lf
*.md    text eol=lf
*.rs    text eol=lf
*.sh    text eol=lf
*.toml  text eol=lf
*.txt   text eol=lf
*.xml   text eol=lf
*.yaml  text eol=lf
*.yml   text eol=lf
*.py    text eol=lf


```

This configuration ensures that for the specified file types:

*   🔄 Line endings are normalized to LF upon check-in.
*   🚫 Conversion to CRLF is prevented when they are checked out.

This helps to prevent newline related issues, such as those that might occur after running the build script.


**Reference:**

* [git commit get fatal error "fatal: CRLF would be replaced by LF in"](https://stackoverflow.com/questions/20168639/git-commit-get-fatal-error-fatal-crlf-would-be-replaced-by-lf-in)
