<div align="center">
  <img src=".github/logo-w-title.png" width="512">
</div>

---

<h4 align="center">
  A data mining suite for DNA microarrays
</h4>

<p align="center">
  <a href="http://candis.readthedocs.io">
    <img src="https://readthedocs.org/projects/candis/badge/?version=latest"/>
  </a>
  <a href="https://saythanks.io/to/achillesrasquinha">
    <img src="https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg?style=flat-square">
  </a>
  <a href="https://paypal.me/achillesrasquinha">
    <img src="https://img.shields.io/badge/Donate-%24-blue.svg?style=flat-square">
  </a>
</p>

![](.github/ria.gif)

<div align="justify">
**candis** is an open source data mining suite (released under the [GNU General Public License v3](LICENSE)) for DNA microarrays that consists of a wide collection of tools you require, right from Data Extraction to Model Deployment. **candis** is built on top of the toolkit - [CancerDiscover](http://github.com/HelikarLab/CancerDiscover) written by the bioinformaticians at [HelikarLab](helikarlab.org).
</div>

**WARNING**

### Table of Contents
* [Installation](#installation)
* [Usage](#usage)
* [Features](#features)
* [Dependencies](#dependencies)
* [License](#license)

### Installation
Download or clone the repository as follows:
```console
$ git clone --recursive http://github.com/achillesrasquinha/candis.git && cd candis
```

Install necessary dependencies:

***Python***
```console
$ pip install -r requirements.txt
```

***R***
```console
$ cd R && Rscript setup.R
```

Then, go ahead and simply:
```console
$ python setup.py install
```

### Usage
**Launching the RIA (Rich Internet Application)**

via CLI
```
$ candis
```
OR
```
$ python -m candis
```

via Python
```python
>>> import candis
>>> candis.main()
```

**Using the CLI (Command Line Interface)**

```
$ candis --cdata path/to/data.cdata --config path/to/config.json
```

### Features
* Converting a CDATA to an **ARFF** file

  ```python
  >>> import candis
  >>> cdata = candis.cdata.read('path/to/data.cdata')
  ```

  Then, simply use the `CData.toARFF` API:

  ```python
  >>> cdata.toARFF('path/to/data.arff')
  ```

* Running a `Pipeline`.
  ```python
  >>> pipe = candis.Pipeline()
  >>> pipe.run(cdata)
  >>> while pipe.status == candis.Pipeline.RUNNING:
  ...     # do something while pipeline is running
  ```

### Demo
Check out a live demo of the application [here](https://cancerdiscover.herokuapp.com).

### Dependencies
* Production Dependencies
  * R
  * WEKA (***NOTE:*** Requires Java)
  * Python 2.7+ or Python 3.5+
* Development Dependencies
  * [Node.js](https://nodejs.org)
  * [SASS](http://sass-lang.com)

### License
This software has been released under the [GNU General Public License v3](LICENSE).
