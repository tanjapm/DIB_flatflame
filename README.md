# Cantera calculatios for premixed laminar flat Methane-Air flame
*The code is part of a Mendeley-data entry:*
[Have a look at my data](http://dx.doi.org/10.17632/jvvvgpdy48.3)

## Motivation & simulation conditions
McKenna type (sometimes also referred to as Kaskan type) burners allow to get experimentally close to the theoretical concept of a 1D flame. You can find them in many combustion labs and they allow to study fundamental concepts. The concept of one-dimensionally flames is a great way to dive into combustion science and cantera is an open-software tool that allows you to do that. After experimentally characterising several flame conditions in the lab, I decided to also do some simulations to have an idea of the theoretical values to be expected. The notebook is (hopefully) well annotated so all informatino can be found there.

I used the following intial conditions:
- gas mixture are at room temperature (300K) and 
- standard pressure (101.325 kPa) 
- with the computational domain spanning 30 mm above the burner exit.


The burner looks like this: <br>
<img src="https://github.com/tanjapm/DIB_flatflame/blob/main/flatflame.JPG" width="400">

CSV files for eleven fuel/air ratios contain the spatial evolution of velocity, density, temperature and species across the grid. The additional jupyter notebook (ThermoPropertiesNASA) and yaml file (thermoDataNASA-9) provide the functions and thermal properties called by the main notebook.

## Installation
just peeking? Github allows you to preview the jupyternotebook _DIB_PelzmannT_CH4air_calculations.ipynb_ or you can use [nb viewer](https://nbviewer.jupyter.org/) using the link to the repository.

If you want to edit and play around with the code you have two options:
- download and run it locally on your pc
- using [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tanjapm/DIB_flatflame/HEAD)


In case jupyter notebook is locally not installed, a [fully editable version](https://mybinder.org/v2/gh/tanjapm/DIB_flatflame/HEAD) is available using BinderHub. The executable notebook environement instance allows to switch to a jupyterlab environment by changing the last part of the url _"tree"_ to _"lab"_. In case the notebook is called in such virtual environment, the command loading the csv files has to be slightly altered by removing the path variable from the 'os.path.join()' method:
```
#path = 'mypath'
allFiles = glob.glob(os.path.join("*.csv")
```

##  How to use?
The jupyternotebook has two main parts, where in the first we calculate the desired properties and create individual csv files. This is the time consuming part of the code. If you want to skip the step and just load the files that are uploaded to the repository, the second part loads this files into a dataframe that you can play with.


## Credits
Cantera is awesome and free. See for yourself: [cantera.org](https://cantera.org/)
David G. Goodwin, Raymond L. Speth, Harry K. Moffat, and Bryan W. Weber. Cantera: An object-oriented software toolkit for chemical kinetics, thermodynamics, and transport processes. https://www.cantera.org, 2018. Version 2.4.0. doi:10.5281/zenodo.1174508

I also used the publicly available [NASA Glenn Coefficients](https://ntrs.nasa.gov/citations/20020085330).


## License
MIT &copy; tanjapm
