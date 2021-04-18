# Convention Handbook for opendata.swiss

## About

Convention handbook on the application and further development of the
DCAT-AP-CH.

The handbook is implemented with Sphinx.

## Installation

The handbook uses Python3:

Set up a virtual environment:

```
python3 -m venv p3venv 
cd ogdch-convention-handbook
``` 

With the virtualenv activated: install the requirements:

```
source p3venv/bin/activate
(p3venv)pip install -r requirements.txt 
```

## Build the Documentation

The documentation can be built locally:

```
(p3venv)cd docs
(p3venv)make clean
(p3venv)make html
```

## Use

No special server is needed: 

- go to docs/build/html and 
- run `index.html` in a browser of your choice

## Linkchecker

The documentation includes a check of its external links.

You can run it with make:

```
(p3venv)make linkcheck
``` 
