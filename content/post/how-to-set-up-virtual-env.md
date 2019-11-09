---
title: "How to Set Up a Virtual Environment"
description: "A short tutorial for configuring a virtual environment in your Python project."
#date: "2019-05-03"
lastmod: "2019-11-09"
include_date: false
include_lastmod: true
#author: "Matt Phillips"
#author_github: "imattman"
header_image: "/img/keyboard-closeup.jpg"
images:
- "/img/ogp-preview-python-tools-500.jpg"
include_toc: true
tags: ["venv", "pip"]
aliases:
- "/venv"
- "/virtualenv"
---

# Motivation

Python applications often require different versions of libraries that can conflict when multiple projects are used on the same system.  Virtual environments provide a way to avoid this problem by isolating each project into its own sandbox, keeping downloaded libraries separate from other projects.

Learning to use virtual environments can seem like a hassle and a bit cumbersome at first.  In the long run, regular use of virtual environments will become second nature and can save you a lot of pain and frustration.


# Windows Quick Start

These instructions use the Windows command line and assume you already have [Python 3.3+][python_download] installed and included in the PATH.

  1. Launch a command terminal:  
    Press `Win-R` (windows key + `r`) to bring up the Run menu.  
    Type `cmd` and press Enter.

  2. Change to your project directory.  
    ```
    cd path\to\my-project
    ```
  3. Create a new virtual environment configuration using Python and the **venv** library.  
    ```
    python -m venv venv
    ```
  4. Activate your virtual environment by running the _activate_ script located under the new `venv` directory.  
    ```
    venv\Scripts\activate
    ```
  5. Install additional packages with `pip`.  
    Individual packages can be installed with `pip install` and the library name.  
    ```
    pip install flask
    ```
    A list of packages contained in a requirements file can be installed using the `-r` flag.  
    ```
    pip install -r requirements.txt
    ```
  6. Add a `.gitignore` file to the root of your project if one doesn't exist.  
    If the file does exist verify it contains a line with `venv`.  
    
    See [gitignore.io][gitignore] for easy generation of file contents ([example][gitignore_example] with common tools)  
    
    **Note:** the name of the file must be `.gitignore`


# Mac & Linux Quick Start

These instructions use the Unix command line and assume you already have [Python 3.3+][python_download] installed and included in the PATH.

  1. Launch a terminal:  
    - Mac: Press `CMD-Space` to bring up Spotlight and enter `terminal`
    - Linux: press `CTL-ALT-T` to launch a terminal

  2. Change to your project directory.  
    ```
    cd path/to/my-project
    ```
  3. Create a new virtual environment configuration using Python and the **venv** library.  
    ```
    python3 -m venv venv
    ```
  4. Activate your virtual environment by sourcing the _activate_ script located under the new `venv` directory.  
    ```
    source venv/bin/activate
    ```
  5. Install additional packages with `pip`.  
    Individual packages can be installed with `pip install` and the library name.  
    ```
    pip install flask
    ```
    A list of packages contained in a requirements file can be installed using the `-r` flag.  
    ```
    pip install -r requirements.txt
    ```
  6. Add a `.gitignore` file to the root of your project if one doesn't exist.  
    If the file does exist verify it contains a line with `venv`.  
    
    See [gitignore.io][gitignore] for easy generation of file contents ([example][gitignore_example] with common tools)  
    ```
    curl -s 'https://www.gitignore.io/api/code,python,pycharm' > .gitignore
    ```
    
    **Note:** the name of the file must be `.gitignore`  

# General Tips

  * Always **activate** the virtual environment (step 4) anytime you start a new command terminal, otherwise the packages installed in that environment won't be found.
  * Use the `deactivate` command when finished with a project and you want to continue using the same terminal (e.g. work on a different python project with its own virtual environment).
  * The `venv` directory contains information specific to your computer and shouldn't be checked into Git.  This is one of the main reasons for the explicit step to add a `.gitignore` file... and it's a good practice :sunglasses:
  * GitHub offers an option to "Add `.gitignore`" when you create a new project.  
    Select "Python" in the list for a shortcut on step 5.
  * [Pypi.org](https://pypi.org) is where `pip` finds the packages it downloads.  The PyPi website offers search options for when you don't know exactly which package to use.

# Troubleshooting

If python isn't found in **step 3** then it's possible your **PATH** needs to be updated.

## Windows

Use `where` to verify **python** is in your **%PATH%**.  
This should list one or more full paths to **python.exe**.  

```
where python
```

If a path to python isn't listed then you will need to locate where `python.exe` resides on your file system and add that directory to your PATH within the [control panel][win_env_path].

## Mac / Linux

Use `which` to verify **python** is in your **$PATH**.  
This should list the full path to a **python3** binary.

```
which python3
```

Mac users who installed python3 using **homebrew** should verify `/usr/local/bin` is in their PATH  

```
echo $PATH
```  

Update the PATH if absent (consider adding this to your `~/.bashrc`)  

```
export PATH="/usr/local/bin:$PATH"
```  

_If that still doesn't work, reach out in Slack._


# Additional Resources

  * [Download the latest Python distribution][python_download]
  * [Python documentation][python_docs] on the `venv` library and virtual environments
  * [Python Module of the Week][pmotw] article on virtual environments
  * [Real Python virtual environment][real_python_venv] primer
  * [Real Python pip][real_python_pip] article



[python_download]: https://www.python.org/downloads/
[gitignore]: https://www.gitignore.io/
[gitignore_example]: https://www.gitignore.io/api/code,python,pycharm,virtualenv
[win_env_path]: https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/
[python_docs]: https://docs.python.org/3/tutorial/venv.html
[pmotw]: https://pymotw.com/3/venv/
[real_python_venv]: https://realpython.com/python-virtual-environments-a-primer/
[real_python_pip]: https://realpython.com/what-is-pip/

