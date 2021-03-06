# Pisces

Pisces is a Python library that connects your geophysical analysis environment
to a SQL database that uses the Center for Seismic Studies (CSS) 3.0 or NNSA KB
Core table schema.

Documentation: <http://jkmacc-lanl.github.io/pisces>

Repository: <https://github.com/jkmacc-LANL/pisces>

[![Build Status](https://travis-ci.org/jkmacc-LANL/pisces.svg?branch=master)](https://travis-ci.org/jkmacc-LANL/pisces)
[![Build status](https://ci.appveyor.com/api/projects/status/w36hbk96bw9lmrnr/branch/master?svg=true)](https://ci.appveyor.com/project/jkmacc-LANL/pisces/branch/master)

## Features

* Import/export waveforms directly to/from your database.  
* Build database queries using Python objects and methods
    ([SQLAlchemy](http:/www.sqlalchemy.org)), not by concatenating SQL strings.
* Integration with [ObsPy](http://www.obspy.org).
* Geographic filtering of results.


## Installation

Requires:

* ObsPy
* Click
* C compiler

Install from [PyPI](https://pypi.python.org/pypi):

```
pip install pisces-db
```

Install current master from GitHub:

```
pip install git+https://github.com/jkmacc-LANL/pisces
```

# Recent History 

([full change log](CHANGELOG.md))

## 0.2.2

### Changes

* `pisces.util.get_tables`, `pisces.util.make_tables`, and
  `pisces.util.get_or_create_tables` are deprecated and will raise a warning.
* `pisces.request.get_waveforms` now has a `tol` keyword that will raise an
  exception if any returned waveform is not within `tol` seconds from the
  requested starttime/endtime.
* Added `--bbfk` flag to `pisces sac2db`, which uses the broadband f-k (BBFK)
  convention of reading x, y array offset distances in the USER 7, 8 SAC
  header variables and storing them Site.dnorth and Site.deast.
* Windows support!  Thanks to @mitchburnett!  e1 and convert C libraries now
  build (using MSVC).
* Automated testing on Mac OSX, Linux, and Windows 7, for Python 2.7 and 3.4,
  thanks to Travis CI and Appveyor.
* Require ObsPy > 1.0

### Bug fixes

* Fixed sac2db wfdisc.foff (issue #12) and wfdisc.dir (issue #11) handling.


