# python-module-template

I created this template because I'm tired of trying to remember all of the correct settings, directory structure, files for a basic python module.  This repo is just a template that I use to get started.

This module template works with PyPi and with pip.  You can find more information at [PyPi Packaging](https://packaging.python.org/en/latest/tutorials/packaging-projects/)

# Using this template

## Create a new repo

These instructions assume you have a working understanding of how to use GitHub and `git`.  If you need help, there are plenty of documentation resources all over the web.

Create a completely empty repo.  This means that underneath the section where you can select Public or Private, do not click the "Add a README file", do not select a .gitignore and do not choose a license.  You will be able to setup your license later.  The other two files are provided for you in this template.

For the name of this repo, I use the same name that I'm going to use for the module.  If there are underscores ('_') in the module name, then I use hyphens ('-') instead.  This is just a thing that I do because I want the directory that gets created when I clone the repo to be different than the module name.

After the repo is created, don't leave the screen that shows up.  You'll need the URL for this page -- we will edit a file named 'pyproject.toml' and this url is the `<< GITHUB REPO URL >>`.

Also on this page is a value that looks like `git@github.com:<< GITHUB USERNAME >>/<< GITHUB REPO NAME >>.git`.  We are going to call the value `<< GITHUB REPO URI >>`

## Clone this repo

Next, clone this repo onto your computer/server.  Run the command below in a directory where you want to work.  When it completes, you'll have a directory called `python-module-template`.  Do not rename this directory.  This name will magically go away in a future step when you push this module to your own repo.

```
prompt> git clone https://github.com/garzola/python-module-template.git
```

## Re-initialize Git

After you clone this repo, you'll have a clean checkout of the template.  The thing is that you want to start with a clean history.  In order to do that, we are going to remove the `.git` directory.  Then we are going to create a clean history.  Later, after we edit some files with your information, we'll check everything in.

```
prompt> cd python-module-template
prompt> rm -rf .git
prompt> git init .
```

## Keep or delete `workspace.code-workspace`

Delete the `workspace.code-workspace` if you do not use Visual Studio Code.  Replace the file if you have one you like better.  Using this file is entirely up to you.

## Edit pyproject.toml

Using your favorite editor, you will need to change values in the `pyproject.toml` file.  You can find out more about `pyproject.toml` at [PyPi Packaging](https://packaging.python.org/en/latest/tutorials/packaging-projects/).

Replace `<< MODULE NAME >>` with whatever you want to call your module.  This name needs to be a legal python module name.  You can check out [PEP 8](https://peps.python.org/pep-0008/#package-and-module-names) for more information about module names.

Replace `<< GITHUB USERNAME >>` with your GitHub username.  If you choose to upload your module to [PyPi.org](https://pypi.org/), this will help keep your package name unique.

Replace `<< SOME KEYWORDS >>` with a list of comma separated strings.  For example:

```
keywords = ['SQLAlchemy', 'Flask', 'SQL',]
```

Replace `<< DEPENDENCIES >>` with a list of comma separated strings.  Use the same format that you would use in a `requirements.txt` file.  For example:

```
dependencies = [
    'Flask',
    'sqlalchemy',
    'sqlalchemy-utils',
]
```

Replace `<< GITHUB REPO NAME >>` with the repo URL -- the url noted in the "Create a new repo" step.

You can add/edit/remove values to fit your needs.  You can find more information at [PyPi Packaging](https://packaging.python.org/en/latest/tutorials/packaging-projects/)

## Edit README-template.md

Use your favorite editor to edit the `README-template.md` file.  Use however much of the template matches your need or replace it entirely.  When you finish, save your work.  Then delete the existing `README.md` -- -incidentally, this file is the one your are reading.  You can also find a copy of this file on GitHub at https://github.com/garzola/python-module-template/blob/main/README.md.

Once the `README.md` file has been removed, rename `README-template.md` to `README.md`.

## Change the module directory name

In the `src` directory, you'll find a directory name `python_module_template`.  Rename this directory to the name of your python module.  This is the same value you replaced <`< MODULE NAME >>` with in `pyproject.toml`.

## Create an initial commit

From the directory that contains the pyproject.toml file, run the following commands:

```
prompt> git add .
prompt> git commit -m 'initial commit'
prompt> git remote add origin << GIT REPO URI >>
prompt> git branch -M main
prompt> git push -u origin main

```

## Refresh the GitHub Repo page

If you did not get an errors on the last step, you can reload the repo page on GitHub.  You should see whatever you put in the README.md file

## Remove this checkout

Remove / Delete the `python-module-template` directory

## Clone your module

Clone your module directly from GitHub.  When you complete this step, the directory name should match the name of the repo on GitHub.

```
prompt> git clone << GIT REPO URI >>
```

# All done

At this point, you can start working on the module itself.

## Pip

If you want to bring this module into a project directory from GitHub, use the following line (edit with your repo URI) in your requirements.txt file

For HTTPS -- public repo:

```
python_module_template-garzola @ git+https://github.com/garzola/python-module-template.git
```

For SSH -- public or private repo:

```
python_module_template-garzola @ git+ssh://git@github.com/garzola/python-module-template.git
```
