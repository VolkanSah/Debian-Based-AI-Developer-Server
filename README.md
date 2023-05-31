# Debian-Based AI Developer Server
This repository provides steps to set up an OpenAI development environment on your Debian-Based system and under Windows Subsystem for Linux (WSL).
## Table of Contents

- [Setting Up Your Environment](#setting-up-your-environment)
  - [Python Installation](#python-installation)
  - [pip Installation](#pip-installation)
  - [OpenAI Library Installation](#openai-library-installation)
- [Optional But Useful Libraries](#optional-but-useful-libraries)
- [Virtual Environment](#virtual-environment)
- [Version Control](#version-control)
- [Using Debian on WSL](#using-debian-on-wsl)
  - [Starting WSL](#starting-wsl)
  - [Installing a WSL Distribution](#installing-a-wsl-distribution)
  - [Stopping WSL](#stopping-wsl)
  - [Uninstalling a WSL Distribution](#uninstalling-a-wsl-distribution)
  - [Listing Installed WSL Distributions](#listing-installed-wsl-distributions)


## Setting Up Your Environment
### Python Installation
Debian comes with Python 3.7 pre-installed, but it's likely you'll want the latest version of Python. Here are the steps to update Python:

First, update your package manager. Run the following commands in your terminal:
```bash
sudo apt-get update
sudo apt-get upgrade
```
Next, install the required dependencies. Run:
```bash
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
xz-utils tk-dev libffi-dev liblzma-dev git openssh-server
```
Then, install pyenv, a tool for managing Python versions. Run:
```bash
curl https://pyenv.run | bash
```
Add pyenv to your shell startup script. Run:
```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bashrc
exec "$SHELL"
```

Finally, install the latest Python version using pyenv. Run:
```bash
pyenv install 3.9.5
pyenv global 3.9.5
```
Check your Python version with:
```bash
python --version
```
#### pip Installation
pip is Python's package manager that you will use to install the OpenAI library. In the latest version of Python, pip should be pre-installed. You can check this by running:
```bash
pip --version
```
If pip is not installed, you can install it with the following command:
```bash
sudo apt install python3-pip
```
#### OpenAI Library Installation
With pip, you can install the OpenAI library. Run the following command:
```bash
pip install openai
```
### Finished!  You can now Install Apache, MariaDB or something else to work on it :smile:

### Optional But Useful Libraries

`requests`: This is a basic library for sending HTTP requests. It's very useful if you want to interact directly with the OpenAI API instead of using the official OpenAI library.
```bash
pip install requests
```
`click`: This library helps you create beautiful command-line interfaces. It has many features that make your life easier, such as automatic generation of help pages, and support for command groups and arguments.
```bash
pip install click
```
`python-dotenv`: With this, you can load environment variables from a .env file in your project. This is very useful to securely store sensitive information such as your OpenAI API key.
```bash
pip install python-dotenv
```
`pytest`: This is a test library for Python, which ensures that your CLI tool works as expected.
```bash
pip install pytest
```
`setuptools`: Once you've created your CLI tool, you can convert it into a Python library that other developers can use as a plugin for their own projects. A common way to do this is using setuptools, a library for creating Python distributions.
```bash
pip install setuptools
```
Note that you can upgrade any of these packages using pip install --upgrade <packagename> to make sure you have the latest version.

Virtual Environment
This is especially important when you're working on multiple Python projects at the same time. Virtual environments allow you to keep the package dependencies for each project separate, leading to fewer conflicts and easier debugging. You can use the virtualenv package to create virtual environments in Python.

```bash
pip install virtualenv
```
And then create a new virtual environment with:

```bash
virtualenv venv
```
Activate the environment with:

```bash
source venv/bin/activate
```
Now, any Python packages that you install are confined to this environment and won't affect your global Python installation.

### Using Debian on WSL
Starting WSL
WSL is automatically started when you open it. You can do this by simply typing "wsl" in PowerShell:

```powershell
wsl
  ```
This opens a new WSL instance with the default distribution. If you want to start a specific distribution, you can provide its name as an argument, e.g.,:

```powershell

wsl -d Ubuntu
  
```
Installing a WSL Distribution
You can install a new WSL distribution from the Microsoft Store. The exact command depends on the specific distribution you want to install. For example, to install Ubuntu 20.04, you could run:

```powershell
wsl --install -d Debian
```
Stopping WSL
You can stop a running WSL instance by typing "exit" at the WSL command line. To stop all running WSL instances, you can run the following command in PowerShell:

```powershell
wsl --shutdown
```
Uninstalling a WSL Distribution
If you no longer need a WSL distribution, you can uninstall it with the following command:

```powershell
wsl --unregister <DistributionName>
```
  Note that this will delete all data in the distribution.

Listing Installed WSL Distributions
You can display a list of all installed WSL distributions by running the following command in PowerShell:

```powershell
wsl --list --verbose
```
### Thanks
**"Thank you! Your support is appreciated, and I would be grateful if you could share this project with others,  giving a :star: to my projects, or  
[becoming a 'Sponsor'](https://github.com/sponsors/volkansah). Don't forget to follow me for more free ideas and updates!"**

### Credits
- Volkan (Sah) Kücükbudak
- [VolkanSah on Github](https://github.com/volkansah)
- [Developer Site](https://volkansah.github.io)

### License
This project is copyright © [VolkanSah](https://github.com/volkansah) and is licensed under the [MIT LICENSE](LICENSE). You are free to use, modify, and distribute the code and assets, as long as the copyright notice and permission notice are preserved in all copies or substantial portions of the software."









