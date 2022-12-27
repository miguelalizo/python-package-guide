# Python Package Documentation

In addition to a well designed [README.md file](readme-file-best-practices), and a  
[CONTRIBUTING.md file](contributing-file), 
there are several core components of Python package documentation, 
including:

* **User-facing documentation website:** This refers to easy-to-read documentation that helps a user work with your package. This documentation should help users both install and use the functionality of your package.  
* **API documentation:** API documentation is generated from [docstrings](https://pandas.pydata.org/docs/development/contributing_docstring.html) found in your code. Ideally you have docstrings for all user-facing functions, methods and classes in your Python package. 



```{note}
Examples of documentation that we love:

* [geopandas](https://geopandas.org/en/stable/)
    * [View rst to create landing page](https://raw.githubusercontent.com/geopandas/geopandas/main/doc/source/index.rst)
* [verde](https://www.fatiando.org/verde/latest/)
    * [View verde landing page code - rst file.](https://github.com/fatiando/verde/blob/main/doc/index.rst)
* [Here is our documentation if you want to see a myST example of a landing page.](https://github.com/pyOpenSci/python-package-guide/blob/main/index.md)
```

In addition to a well designed [README FILE](readme-file-best-practices), and a 
[contributing file](contributing-file), 
there are several core components of Python package documentation, 
including:

* **User-facing documentation:** This refers to easy-to-read documentation that helps a user work with your package. This documentation should help users both install and use the functionality of your package.  
* **API  documentation:** API documentation is generated from [docstrings](https://pandas.pydata.org/docs/development/contributing_docstring.html) found in your code. Ideally you have docstrings for all user-facing functions, methods and classes in your Python package.  

## User-facing documentation for your Python package: 

User-facing documentation should be published on a easy-to-navigate website. All language should be written with non-developer users in mind. This means 
using language that is less technical.

A few tips to make sure your documentation is accessible include: 

* Whenever possible, define technical terms and jargon.
* Consider writing instructions for a high-school level reader. 
* Include step by step code examples, tutorials or vignettes that support getting started using your package.



## API's and Docstrings

### What is an API?

API standards for **A**pplied **P**rogramming **I**nterface. When 
discussed in the context of a (Python) package, the API refers to 
the interface and tools that you, as a package user, use in a package. 

A simple example of a package API element:
For instance, a package might have a function called `add_numbers()` 
that adds up a bunch of numbers. To add up numbers, you as the user 
simply call `add_numbers(1,2,3)` and the package function calculates the value and returns `6`. In using the `add_numbers` function, a user is 
using the package's API. 

 Package API's can consist of functions and/or classes (or object) that provide an easier-to-user interface (the API) for a user. 

### What is a docstring and how does it relate to documentation? 
In Python a docstring refers to text in a function, method or class 
that describes what the function does and its inputs, outputs and what it 
returns.

The docstring is thus important for:

* When you, as a user, call `help()` e.g. `help(add_numbers)` in Python, it returns the elements in your docstring to help guide a user towards using the function more effectively. 
* When you build your package's documentation, the docstrings can be also used to automagically create full API documentation that provides a clean view of all functions methods and classes in a package.  

```{tip}
Example API Documentation (Documentation for all functions and classes in a package)
* [View example high level API documentation for the Verde package. This page lists every function and class in the package along with a brief explanation of what it does](https://www.fatiando.org/verde/latest/api/index.html)
* [You can further dig down to see what a specific function does within the package by clicking on an API element](https://www.fatiando.org/verde/latest/api/generated/verde.grid_coordinates.html#verde.grid_coordinates)
```


### What tools to use to build your documentation: sphinx

Most python packages use [sphinx](https://www.sphinx-doc.org/) to build their documentation. 
Sphinx has documentation themes that are easy to apply and help you quickly and easily build an easy-to navigate website.

Sphinx also offers extensions that support:

* [automatically documenting your API using docstrings in your code](https://www.sphinx-doc.org/en/master/usage/extensions/autodoc.html)
* [running and testing code examples in your docstrings (doctest)](https://www.sphinx-doc.org/en/master/usage/extensions/doctest.html)

While you are free to use whatever sphinx theme you prefer,
the most common modern templates that recommend for the Python scientific 
community are:  

* [pydata-sphinx-theme](https://pydata-sphinx-theme.readthedocs.io/) 
* [sphinx-book-theme](https://sphinx-book-theme.readthedocs.io/)
* [furo](https://pradyunsg.me/furo/quickstart/)

All of the above themes support [myst](https://myst-parser.readthedocs.io/) 
which allows you to build your package documentation in using `markdown` 
rather than `.rst`. More on that below.

```{tip}
This book is created using sphinx and the `furo` theme.
```

### myST vs rst syntax to create your docs 
There are two commonly used syntaxes for creating docs:

1. [myST:](https://myst-parser.readthedocs.io/en/latest/intro.html) myST is a fusion of markdown and rST. It is a nice option if you are more comfortable writing markdown. But more flexible than markdown. 
2. [rST:](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html) this is the native syntax that sphinx supports. 

Markdown is often a preferred syntax to use because:

* It is often thought to be simpler and thus easier to learn;
* Most of your core python package text files, such as your README.md file, are already in `.md` format
* `GitHub` and `Jupyter Notebooks` support this default text file format.

There is no wrong or right when choosing a syntax to write your documentation. 
Choose whichever syntax works best for you and your community! 

```{tip}
If you are on the fence about myST vs rst, you might find that *myST* is easier 
for more people to contribute to.  
```

### How to host your Python package documentation

We suggest that you setup a website to host your documentation. There are two 
ways to do quickly create a documentation website:

1. You can host your documentation yourself using [GitHub Pages](https://pages.github.com/) or another online hosting service. 
2. You can host your documentation using [Read the Docs](https://readthedocs.org/).

If you don't want to maintain a documentation website for your Python package, 
we suggest using Read the Docs. Read the Docs allows you to:

* Quickly launch a website using the documentation found in your GitHub repository.  
* Track versions of your documentation as you release updates.



## Documentation landing page best practices 

To make it easy for users to find what they need quickly, all packages should 
have 4 elements on the home page of their documentation:

* **Getting started:** This section should provide the user with a quick start for installing your package. A small example of how to use the package is good to have here as well. 
* **About:** Describe your project, state project goals and what it does. 
* **Community:** Instructions for how to help and/or get involved. This section might include a development guide. 
* **Documentation:** The actual project documentation. You may have two sections of documentation - the user facing documentation and your API reference. 

NOTE: in many cases you can include your **README** file and your **CONTRIBUTING** files 
in your documentation given those files may have some of the components listed above.

`````{tip}
You can include files in sphinx using the include directive.
Below is an example of doing this using `myst` syntax. 
````
```{include} ../README.md
```
````
`````

## Python package API documentation 

API documentation refers to explanation about the function, inputs and outputs 
of every (*within reason*) function, class, method in your package. API documentation
in python requires that you use a docstring for each class, function or method that:

* Explains what the function, method or class does 
* Explains what every input and output variable's (type) is (ie. `string`, `int`, `np.array`)
* Explains the expected output `return` of the object, method or function.

### Python docstring format best-practices 

There are several Python docstring formats that you can chose to use when documenting 
your package. We suggest using [numpy-style docstrings](https://numpydoc.readthedocs.io/en/latest/format.html#docstring-standard).

```{tip}
If you are using `numpy-style` docstrings, be sure to include the sphinx napoleon 
extension in your documentation `conf.py` file. This extension allows sphinx 
to properly read and format numpy-style docstrings. 
```

### Docstring examples Better and Best 

Below is a good example of a well documented function. Notice that this function's 
docstring includes all parameter inputs and outputs. The description of the function 
is short and to the point (2 to 3 sentences). And the return of the function is 
specified. 

```Python
def extent_to_json(ext_obj):
    """Convert bounds to a shapely geojson like spatial object.
    This format is what shapely uses. The output object can be used
    to crop a raster image.
    Parameters
    ----------
    ext_obj: list or geopandas geodataframe
        If provided with a geopandas geodataframe, the extent
        will be generated from that. Otherwise, extent values
        should be in the order: minx, miny, maxx, maxy.
    Return
    ------
    extent_json: A GeoJSON style dictionary of corner coordinates
    for the extent
        A GeoJSON style dictionary of corner coordinates representing
        the spatial extent of the provided spatial object.
    """
```

### Best - a docstring with example use of the function

This example contains an example of using the function that is also tested in 
sphinx using [doctest](https://docs.python.org/3/library/doctest.html).

```Python
def extent_to_json(ext_obj):
    """Convert bounds to a shapely geojson like spatial object.
    This format is what shapely uses. The output object can be used
    to crop a raster image.
    Parameters
    ----------
    ext_obj: list or geopandas geodataframe
        If provided with a geopandas geodataframe, the extent
        will be generated from that. Otherwise, extent values
        should be in the order: minx, miny, maxx, maxy.
    Return
    ------
    extent_json: A GeoJSON style dictionary of corner coordinates
    for the extent
        A GeoJSON style dictionary of corner coordinates representing
        the spatial extent of the provided spatial object.
    Example
    -------
    >>> import geopandas as gpd
    >>> import earthpy.spatial as es
    >>> from earthpy.io import path_to_example
    >>> rmnp = gpd.read_file(path_to_example('rmnp.shp'))
    >>> es.extent_to_json(rmnp)
    {'type': 'Polygon', 'coordinates': (((-105.4935937, 40.1580827), ...),)}
    """

```

```{figure} ../images/sphinx-rendering-extent-to-json-earthpy.png
---
name: directive-fig
width: 80%
---
Using the above numpy-style docstring in sphinx, the autodoc extension will 
create the about documentation section for the `extent_to_json` function. The 
output of the `es.extent_to_json(rmnp)` command can even be tested using 
doctest adding another quality check to your package. 
```


