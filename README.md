# Template for Research Projects
================================

## Project Description
----------------------
Abstract-like paragraph that describes the project should go here. 
Overview, general hypothesis, what you did, what you found.

## Project Organization
--------------------
    rs-YEAR-CamelCaseName ──┤
                            ├── DATA.CORE/          <- Symbolic link to the immutable, raw data
                            │ 
                            ├── DATA.RSRCH/         <- Symbolic link to any processed data downstream of the raw data.
                            │ 
                            ├── figures/            <- Figures saved by scripts or notebooks.
                            │
                            ├── notebooks/          <- Jupyter notebooks for analysis only (e.g. statistics, production of graphs). The naming convention should be eNUM-USER_INITIAL-DESCRIPTIVE_TEXT.ipynb
                            │
                            ├── codebase/           <- Collection of Python modules with source code for project.
                            │
                            ├── environment.yml     <- conda virtual environment definition file.
                            │
                            ├── LICENSE
                            │
                            ├── Makefile            <- Makefile with commands like `make environment`
                            │
                            ├── README.md           <- The top-level README for developers using this project.
                            │
                            └── tox.ini             <- tox file with settings for running tox; see tox.testrun.org
---------------

### DATA
Data sets are typically large, sometimes remotely stored, and difficult to version control using Git. To make research development modular, `DATA.*` folders should actually represent symbolic links to raw and non-raw data stores located elsewhere. The advantage of this is that multiple projects can access and operate on the overlapping raw and non-raw data. Another advantage of this is that a centralized repository of the raw and non-raw data can be consistently synchronized across research development machines of different locations. 

### Notebooks 
------------
Notebooks contain all reproducible analysis using functions in Codebase. They must be an immutable ledger of individual steps of the analysis, including what worked and what did not work. Notebooks should also be modular and each notebook should have a clear purpose, intent, or well-described facet of the data that is being explored. Before any code is written, a good practice is to describe the purpose and goal of the notebook in the first cell. 

The notebooks contain scripts that define conditional variables and execute codebase functions using those variables as inputs. A byproduct of a notebook is a task(s) that could be embedded into a pipeline (using pipelining tools such as Luigi). All analysis output related to the notebook should be output into a subfolder of the DATA.RSRCH folder with the name eNUM, where NUM is the numerical ID of the notebook.

### Codebase
------------
The Codebase contains all formatted code in the form of input/output functions. The Codebase is essentially a collection of the individual pipes of the analysis. Important rules to follow are: 
1. Do not hard-code any variables or objects. It is okay to specify default values in function definition, if applicable.
2. Dichotomize code into sub-folders based on functionality.
3. Code is modular and decoupled.

## Tests
--------
All modules and functions in `codebase` must have unit tests associated with it. For a given directory in the codebase, there must be a second-level directory called `tests`. The `tests` directory must contain a py-file called `tests_NAME.py` where NAME is a py-file in the first-level directory.

## Set up
------------
Install the virtual environment with conda and activate it:

```bash
$ conda env create -f environment.yml
$ source activate example-project 
```

Install `codebase` in the virtual environment:

```bash
$ pip install --editable .
```

Run Jupyter Notebook and open the notebooks in `notebooks/`:

```bash
$ jupyter notebook
```
