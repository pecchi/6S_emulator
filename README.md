### What is this repo about?

Atmospheric correction of satellite images. Specifically to convert from:

radiance -> surface reflectance

### How does it work?

This project is written in Python. We use the [6S](http://modis-sr.ltdri.org/pages/6SCode.html) radiative transfer code through a Python wrapper called [Py6S](http://py6s.readthedocs.io/en/latest/introduction.html). 

We build interpolated look up tables ([iLUTs](link)) to get the parameter values we need to [atmospherically correct](link) radiance measured by a satellite sensor.

### Why is this important?

Radiative transfer code (e.g. 6S, MODTRAN, etc.) take a [long time](link) to execute. The use of an iLUT boost performance speeds by a few orders of magnitude with a minimal effect on accuracy (i.e. [within X %](link)). 

### What about MODTRAN?

6S shows good agreement ([i.e. < 0.7 %](http://6s.ltdri.org/files/publication/Kotchenova_et_al_2006.pdf)) with MODTRAN. Some studies indicate that 6S has an edge in terms of accuracy; these include [Monte Carlo](http://6s.ltdri.org/files/publication/Kotchenova_et_al_2008.pdf) and [Ground-Truth](https://www.researchgate.net/publication/263620472_Evaluation_of_atmospheric_correction_models_and_Landsat_surface_reflectance_product_in_an_urban_coastal_environment) approaches.
