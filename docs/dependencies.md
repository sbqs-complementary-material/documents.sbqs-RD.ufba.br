# Poetry - USER GUIDE 

#### This document aims to guide the use of the dependency management package `Poetry`

# How to use

## Step 1 - Installation

First you need to install the `Poetry` in your `Python`environment. You can do this using `pip` , the `Python` 
management package.

**_Install Poetry_**

```sh
pip install poetry
```

**_Upgrade Poetry_**
```sh
pip upgrade poetry
```

**_Delete Poetry_**
```sh
pip uninstall poetry
```

## Step 2 - Basic Usage

### Project Setup

```sh
poetry new my_project
```

The command above will create the `my-project` directory with the following content:
```
my_project
├── pyproject.toml
├── README.md
├── my_project
│   └── __init__.py
└── tests
    └── __init__.py
```

The `pyproject.toml` file is what is the most important here. This will orchestrate your project and its dependencies. 
For now, it looks like this:
```toml
[tool.poetry]
name = "my-project"
version = "0.1.0"
description = ""
authors = ["Jander Junior <jander@junior.br>"]
readme = "README.md"
packages = [{include = "my_project"}]

[tool.poetry.dependencies]
python = "^3.7"


[build-system]
requires = ["poetry-core"]
build-backend = "poetry.core.masonry.api"
```

Poetry assumes your package contains a package with the same name as `tool.poetry.name` located in the root of your 
project. If this is not the case, populate `tool.poetry.packages` to specify your packages and their locations.

Poetry will require you to explicitly specify what versions of Python you intend to support, and its universal locking 
will guarantee that your project is installable (and all dependencies claim support for) all supported Python versions.

For example, in this `pyproject.toml` file above:
```toml
[tool.poetry.dependencies]
python = "^3.7"
```
we are allowing any version of Python 3 that is greater than 3.7.


### Initialising a pre-existing project 

Instead of creating a new project, Poetry can be used to ‘initialise’ a pre-populated directory. To interactively create 
a `pyproject.toml` file in directory `pre-existing-project`:
```sh
cd pre-existing-project
poetry init
```

**_Virtual Environment_**

By default, Poetry creates a virtual environment in `{cache-dir}/virtualenvs`. 

If the virtual environment is not **activated**. Run the following command:
```sh
poetry shell
```
Then the virtual environment will be activated.

However, you can change the `cache-dir` value by editing the Poetry configuration. Additionally, you can use the 
`virtualenvs.in-project` configuration variable to create virtual environments within your project directory. 

**To learn more about virtual environments in poetry, check out the following link:** [Poetry Virtual Environments](https://python-poetry.org/docs/basic-usage/#using-your-virtual-environment)


## Step 3 - Managing Dependencies

### Specifying Dependencies

If you want to **add** dependencies to your project, you can use the `add` command.
```sh
poetry add pandas
```

It will automatically find a suitable version constraint and install the package and sub-dependencies.

**_Update_**

To **update** the latest version of dependencies. Run the following command:
```sh
poetry update pandas
```

Then, your `pyproject.toml` will be updated.

### Dependency Groups

Poetry provides a way to **organize** your dependencies by **groups**. For instance, you might have dependencies that 
are only needed to test your project or to build the documentation.

To declare a new dependency group, use a `tool.poetry.group.<group>` section where <group> is the name of your dependency 
group (for instance, `test`):

```toml
[tool.poetry.group.test.dependencies]
pytest = "^6.0.0"
pytest-mock = "*"
```

**_Optional Groups_**

A dependency group can be declared as **optional**. This makes sense when you have a group of dependencies that are only 
required in a particular environment or for a specific purpose.

```toml
[tool.poetry.group.docs]
optional = true

[tool.poetry.group.docs.dependencies]
mkdocs = "*"
```
Optional groups can be installed in addition to the default dependencies by using the `--with` option of the `install`
command.

```sh
poetry install --with docs
```

### Adding a dependency to a droup

The add command is the preferred way to add dependencies to a group. This is done by using the `--group (-G)` option.

```sh
poetry add pytest --group test
```

_If the group does not already exist, it will be created automatically._

### Installing group dependencies 

By default, dependencies across all **non-optional** groups will be installed when executing `poetry install`.

```textmate
The default set of dependencies for a project includes the implicit main group defined in 
tool.poetry.dependencies as well as all groups that are not explicitly marked as an optional group.
```

**_Exclude one or more groups:_**
```sh
poetry install --without test,docs
```

**_Opt in optional groups:_**
```sh
poetry install --with docs
```

**_Install only specific groups:_**
```sh
poetry install --only docs
```

**_Install the project’s runtime dependencies:_**
```sh
poetry install --only main
```

**_Install the project root, and no other dependencies:_**
```sh
poetry install --only-root
```

**To learn more about groups management, check out the following link:** [Dependencies Management](https://python-poetry.org/docs/managing-dependencies/)


## Step 4 - Other Commands

**_Build_**

The `build` command builds the source and wheels archives.
```sh
poetry build
```

**Note that**, at the moment, only pure python wheels are supported.

**_Check_**

The `check` command validates the content of the `pyproject.toml` file and its consistency with the `poetry.lock` file. 
It returns a detailed report if there are any errors.
```sh
poetry check
```

**_Remove_**

The `remove` command removes a package from the current list of installed packages.
```sh
poetry remove pandas
```

If you want to remove a package from a specific group of dependencies, you can use the `--group (-G)` option:
```sh
poetry remove mkdocs --group docs
```

**_Run_**

The `run` command executes the given command inside the project’s virtualenv.
```sh
poetry run python -V
```
It can also execute one of the scripts defined in `pyproject.toml`.


**_Show_**

To list all the available packages, you can use the `show` command.
```sh
poetry show
```

**To see other command lines options, check out the following link:** [Command Line Options](https://python-poetry.org/docs/cli/)


### This document was developed based on the Poetry documentation available on the website. To learn more about the `Poetry Library`, check out their [Site](https://python-poetry.org/) 