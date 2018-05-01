# pyCompare <img src="docs/_static/pyCompare.png" width="200" style="max-width: 30%;" align="right" />

[![Build Status](https://travis-ci.org/jaketmp/pyCompare.svg?branch=master)](https://travis-ci.org/jaketmp/pyCompare) [![codecov](https://codecov.io/gh/jaketmp/pyCompare/branch/master/graph/badge.svg)](https://codecov.io/gh/jaketmp/pyCompare) ![Python36](https://img.shields.io/badge/python-3.6-blue.svg) [![PyPI](https://img.shields.io/pypi/v/pyCompare.svg)](https://pypi.org/project/pyCompare/)

A Python module to generate [Bland-Altman](https://en.wikipedia.org/wiki/Bland–Altman_plot) plots to compare two measurements.

<img src="docs/_static/bland_altman.png" style="max-width: 80%;" align="center" />

## Installation

To install _via_ [pip](https://pypi.org/project/nPYc/), run:

    pip install pyCompare

Installation with pip allows the usage of the uninstall command

    pip uninstall pyCompare


## Documentation


### blandAltman( )
    blandAltman(data1, data2, limitOfAgreement=1.96, confidenceInterval=None, confidenceIntervalMethod='exact paired', detrend=None, **kwargs)

Generate a Bland-Altman plot to compare two sets of measurements of the same value.

`data1` and `data2` should be 1D numpy arrays of equal length containing the paired measurements.

Confidence intervals on the limit of agreement may be calculated using:
- 'exact paired' uses the exact paired method described by Carkeet
- 'approximate' uses the approximate method described by Bland & Altman

The exact paired method will give more accurate results when the number of paired measurements is low (approx < 100), at the expense of much slower plotting time.

The *detrend* option supports the following options:
- ``None`` do not attempt to detrend data - plots raw values
- 'Linear' attempt to model and remove a multiplicative offset between each assay by linear regression

#### References

- Altman, D. G., and Bland, J. M. “Measurement in Medicine: The Analysis of Method Comparison Studies” Journal of the Royal Statistical Society. Series D (The Statistician), vol. 32, no. 3, 1983, pp. 307–317. [JSTOR](https://www.jstor.org/stable/2987937).
- Altman, D. G., and Bland, J. M. “Measuring agreement in method comparison studies” Statistical Methods in Medical Research, vol. 8, no. 2, 1999, pp. 135–160. [DOI](https://doi.org/10.1177/096228029900800204).
- Carkeet, A. "Exact Parametric Confidence Intervals for Bland-Altman Limits of Agreement" Optometry and Vision Science, vol. 92, no 3, 2015, pp. e71–e80 [DOI](https://doi.org/10.1097/OPX.0000000000000513).