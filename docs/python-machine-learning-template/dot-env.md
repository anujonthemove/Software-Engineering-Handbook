# ⛔ **Credential Management using .env**

The `.env` file is a simple and effective way to manage credentials and other environment-specific settings. Here's how you can use it:

### 🌐 **Store proxy details**

If you're working behind a proxy, you can store your proxy information in the `.env` file. These will be automatically loaded and utilized by `Pipenv` during package installation. Here's the format:

```bash
HTTP_PROXY='http://user:password@your-proxy-url:port'
HTTPS_PROXY='https://user:password@your-proxy-url:port'
```

Replace `user`, `password`, `your-proxy-url`, and `port` with your actual proxy details.


### 🗝️ **Store credentials/secrets/keys**

You can also store API keys and other credentials in the `.env` file. Here's an example of how to store an API key:

```bash
OPENAI_API_KEY='xxxx-xxxx'

```

Replace `xxxx-xxxx` with your actual OpenAI API key.

<!-- To utilize these credentials into your Python code, you can use the `python-decouple` library. This library separates the settings parameters from your source code, allowing your project to be more secure, scalable, and to change configurations easily.

Here's an example of how you can use `python-decouple`:

```python

from decouple import config

# Get the API key
api_key = config('OPENAI_API_KEY')

# Now you can use the api_key variable in your code

```

In this example, `config('OPENAI_API_KEY')` retrieves the value of OPENAI_API_KEY from the `.env` file. You can use this method to retrieve any values stored in the `.env ` file.

_Remember to replace `xxxx-xxxx` in the `.env` file with the actual key you want to retrieve from the variable `OPENAI_API_KEY`._ 
 -->


### 👨‍🔧 **Using .env variables inside Python code**

To utilize the variables defined in the `.env` file into your Python code, we recommend using the `python-decouple` library. This library simplifies the process of separating settings from your source code, making it easier to change these settings without modifying the code itself.

Here's an example of how you can use `python-decouple` to access the credentials stored in your `.env` file:

```python
from decouple import config

# Get the OpenAI API key
openai_api_key = config('OPENAI_API_KEY')

# Get the HTTP proxy
http_proxy = config('HTTP_PROXY')

# Get the HTTPS proxy
https_proxy = config('HTTPS_PROXY')

```

In this code, `config('OPENAI_API_KEY')`, `config('HTTP_PROXY')`, and `config('HTTPS_PROXY')` retrieve the values of `OPENAI_API_KEY`, `HTTP_PROXY`, and `HTTPS_PROXY` from the `.env` file, respectively.



!!! note
    The `.env` file does not get committed to your version control system. It typically contains sensitive information that should not be shared publicly. 

