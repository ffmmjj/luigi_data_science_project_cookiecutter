# Cookiecutter Data Science with luigi

_A logical, reasonably standardized, but flexible project structure for doing and sharing data science work._

***This project provides a Cookiecutter data science project template based on [an existing project template](https://github.com/drivendata/cookiecutter-data-science). This version adds support for [luigi](https://github.com/spotify/luigi) tasks instead of using ad-hoc python for data processing as suggested in the original template.***


#### [Project homepage](http://drivendata.github.io/cookiecutter-data-science/)


### Requirements to use the cookiecutter template:
-----------
 - Python 2.7 or 3.5
 - [Cookiecutter Python package](http://cookiecutter.readthedocs.org/en/latest/installation.html) >= 1.4.0: This can be installed with pip by or conda depending on how you manage your Python packages:

``` bash
$ pip install cookiecutter
```

or

``` bash
$ conda config --add channels conda-forge
$ conda install cookiecutter
```

### To start a new project, run:
------------

    cookiecutter https://github.com/ffmmjj/luigi_data_science_project_cookiecutter

### Installing development requirements
------------

    pip install -r requirements.txt

### Run luigi tasks
------------

    make data

### Clean temporary and processed data
------------
    make data_clean 
    
### Running the tests
------------

    py.test tests

### Adding new luigi tasks
The project comes with a final luigi task called `FinalTask` in the module `src/data_tasks/final.py`.
New tasks must be placed under the directory `src/data_tasks/`. The luigi task that generates the final, processed dataset must be added to the list of tasks required by FinalTask since this is the "data sink" processed by luigi when you use the Makefile's `data` target.

See [the original project](https://github.com/drivendata/cookiecutter-data-science) for more details on this project structure.
