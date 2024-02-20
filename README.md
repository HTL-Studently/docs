# docs
Documentation using MKDocs with the Material Theme
This file serves to demonstrate how to work with and setup MkDocs. To view the actual documentation hosted on GitHub Pages, go to this [page](https://htl-studently.github.io/docs/).


## Installation and Setup 

### Create a virtual environment: 

`python -m venv env`

`source env/bin/activate/`

### Install required packages

Install using the requirements.txt file

`pip install -r requirements.txt`


Alternatively, the required packages can be installed manually  

`pip install mkdocs-material`


### Preview live changes in the browser

`mkdocs serve `

Shows live changes in the [browser](http://localhost:8000)


### Build
Always build before pushing to GitHub. Building generates static html files that can be hosted by GitHub pages. Changes that are not build will not be updated on GitHub Pages.

`mkdocs build`

This should generate files in the /site folder. These files are used by GitHub. The `mkdocs build` command does not start a preview server.

GitHub Pages only uses static files from the 'main' branch. Changes on other branches, build or not, will not be shown on the Page.



## Documentation Guide

### File Structure

Do NOT use screenshots to show file structure. Instead, use the `tree` command.

#### Installation

`sudo apt install tree`

#### Usage

Basic usage

`tree path/to/directory`

Limit depth 

`tree -L <Depth>`