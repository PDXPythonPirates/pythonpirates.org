---
title: "How to Set Up a Virtual Environment"
description: "A short tutorial for configuring a virtual environment in your Python project."
date: 2019-05-03
#author: "Matt Phillips"
#author_github: "imattman"
header_image: "/img/keyboard-closeup.jpg"
images:
- "/img/ogp-preview-python-tools-500.jpg"
include_toc: true
tags: ["venv", "pip"]
---

# Motivation

Python applications often require different versions of libraries that can conflict when multiple projects are used on the same system.  Virtual environments provide a way to avoid this problem by isolating each project into its own sandbox, keeping downloaded libraries separate from other projects.

Learning to use virtual environments can seem like a hassle and a bit cumbersome at first.  In the long run, regular use of virtual environments will become second nature and can save you a lot of pain and frustration.


# Quick Start

#### Windows

  1. Use `where` to verify **python** is in your **%PATH%**.  
  This should list one or more full paths to **python.exe**.
    ```
    where python
    ```
  2. Change to your project directory.
    ```
    cd path\to\my-project
    ```
  3. Create a new virtual environment configuration using Python and the **venv** library.
    ```
    python -m venv venv
    ```
  4. Activate your virtual environment by running the _activate_ script located in the new `venv` directory.
    ```
    venv\Scripts\activate
    ```
  5. Add a `.gitignore` file to the root of your project if one doesn't exist.  
     If the file does exist verify it contains a line with `venv`.  

     See [gitignore.io][gitignore] for easy generation of file contents ([example][gitignore_example] with common tools)  

     **Note:** the name of the file must be `.gitignore`


#### Mac / Linux

  1. Use `which` to verify **python** is in your **$PATH**.  
  This should list the full path to a **python3** binary.
    ```
    which python3
    ```
  2. Change to your project directory.
    ```
    cd path/to/my-project
    ```
  3. Create a new virtual environment configuration using Python and the **venv** library.
    ```
    python3 -m venv venv
    ```
  4. Activate your virtual environment by sourcing the _activate_ script located in the new `venv` directory.
    ```
    source venv/bin/activate
    ```
  5. Add a `.gitignore` file to the root of your project if one doesn't exist.  
     If the file does exist verify it contains a line with `venv`.  

     See [gitignore.io][gitignore] for easy generation of file contents ([example][gitignore_example] with common tools)  
     ```
     curl -s 'https://www.gitignore.io/api/code,python,pycharm' > .gitignore
     ```

     **Note:** the name of the file must be `.gitignore`  

# General Tips

  * **Activate** the virtual environment (_step 4. above_) anytime you start a new command shell, otherwise the packages installed in that environment won't be found.
  * The `venv` contains information specific to your computer and shouldn't be checked into Git.  This is the main reason for the explicit step to add a `.gitignore` file... and it's just good practice :sunglasses:
  * GitHub offers an option to "Add `.gitignore`" when you create a new project.  
    Select "Python" in the list for a shortcut on _step 5._

# Troubleshooting

If python isn't found using the check in _step 1._ then it's likely your **PATH** needs to be updated.

  * Windows users will need to find where `python.exe` resides on their file system and add that directory to their PATH within the [control panel][win_env_path].
  * Mac / Linux users who installed python3 using **homebrew** should verify `/usr/local/bin` is in their PATH  
  ```
  echo $PATH
  ```  
  Update the PATH if absent (consider adding this to your `.bashrc`)
  ```
  export PATH="/usr/local/bin:$PATH"
  ```  
  _If that still doesn't work, reach out in Slack._


# Additional Resources

  * [Python documentation][python_docs] on the `venv` library and virtual environments
  * [Python Module of the Week][pmotw] article on virtual environments
  * [Real Python][real_python] virtual environment primer



[gitignore]: https://www.gitignore.io/
[gitignore_example]: https://www.gitignore.io/api/code,python,pycharmwin_env_path
[win_env_path]: https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/
[python_docs]: https://docs.python.org/3/tutorial/venv.html
[pmotw]: https://pymotw.com/3/venv/
[real_python]: https://realpython.com/python-virtual-environments-a-primer/

