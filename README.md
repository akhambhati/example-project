Template for Research Projects
================================

## Project Description
----------------------
Abstract-like paragraph that describes the project should go here. 
Overview, general hypothesis, what you did, what you found.

<<<<<<< HEAD
## Project Organization
--------------------
rs-{YEAR}-{CamelCaseName}
    │
    ├── DATA.CORE/          <- Symbolic link to the immutable, raw data
    │ 
    ├── DATA.RSRCH/         <- Symbolic link to any processed data downstream of the raw data.
    │ 
    ├── figures/            <- Figures saved by scripts or notebooks.
    │
    ├── notebooks/          <- Jupyter notebooks for analysis only (e.g. statistics, production of graphs).
    │                          Code for transforming/processing/modelling data should **not** be contained here.
    │
    ├── codebase/           <- Collection of Python modules with source code for project.
    │
    ├── tests/              <- Unit tests for the codebase.
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
=======
Project Organization
>>>>>>> 6c19a050754d06a4f73d70ae189f7ea1703805d2
--------------------
    rs-YEAR-CamelCaseName ──┤
                            │
                            ├── data/               <- The original, immutable data dump. 
                            │
                            ├── figures/            <- Figures saved by scripts or notebooks.
                            │
                            ├── notebooks/          <- Jupyter notebooks. Naming convention is a short `-` delimited 
                            │                         description, a number (for ordering), and the creator's initials,
                            │                        e.g. `initial-data-exploration-01-hg`.
                            │
                            ├── output/             <- Manipulated data, logs, etc.
                            │
                            ├── tests/              <- Unit tests.
                            │
                            ├── exampleproject/     <- Python module with source code of this project.
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

## Jupyter Notebooks 
------------
TODO

## Codebase
------------
TODO

## Set up
------------

Install the virtual environment with conda and activate it:

```bash
$ conda env create -f environment.yml
$ source activate example-project 
```

Install `exampleproject` in the virtual environment:

```bash
$ pip install --editable .
```

Run Jupyter Notebook and open the notebooks in `notebooks/`:

```bash
$ jupyter notebook
```
