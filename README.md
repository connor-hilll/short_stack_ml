# Short Stack Sustain Machine Learning Talk

## Getting Started
### General Prerequisites
**_NOTE:_**  The suggested code  instructions are for macOS

#### Install Visual Studio Code

Install Visual Studio Code here: https://code.visualstudio.com/

##### Add VS Code to your PATH

Follow instructions here https://www.freecodecamp.org/news/how-to-open-visual-studio-code-from-your-terminal/

#### Installing brew and necessary packages

Use the brew package manager to install requirements before setting up the repo. Visit https://brew.sh for installation instructions for the package manager and then enter following command to install requirements.

```
brew install python@3.10
```

#### Installing python through pyenv

Installation of Python can also be done through [pyenv](https://github.com/pyenv/pyenv) which can be installed through brew.

```sh
brew install pyenv

# Make sure to update x with the correct version of 3.10 in use. You may list all versions of 3.10 by executing
# pyenv install 3.10

pyenv install 3.10.x
pyenv global 3.10.x
pyenv user 3.10.x
```

If you are using zsh, execute the following to make sure the python command will link properly to the version installed
through pyenv:

```sh
echo 'eval "$(pyenv init --path)"' >> ~/.zprofile

echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```

## Instructions for Setup

### Clone the Repository

```
git clone git@github.com:connor-hilll/short_stack_ml.git
```

### Setting up via CLI

Follow these instructions and run the commands from the root of the repo.

1. Create Virtualenv:
   - `python3 -m venv venv`

2. Activate venv:
   - `. venv/bin/activate`

3. Install requirements:
   - `pip3 install -r requirements.txt`

4. Install new kernal:
   - `ipython kernel install --user --name=short_stack_ml`

5. Open in VS Code:
   - `code .`
     - Note: VS Code must be added to your path. Reference `Add VS Code to your PATH` section above

6. Ensure iPython Notebook is using the virtual environment:
   - In the `energy_analysis.ipynb` file, in the top right corner, it should state that the kernal is `venv (Python 3.x.x)`


## Notes

### Packages

The main packages used are as follows:
   1. Pandas - data analysis and manipulation tool
   2. Numpy - fundamental package for scientific computing
   3. StatsModels - provides classes and functions for the estimation of many different statistical models
   4. Scikit-learn - Simple and efficient tools for predictive data analysis
   5. Matplot lib - Plotting library
   6. iPython - Provides a rich toolkit to help you make the most of using Python interactively

Some of the librarys have overlap such as scikit-learn and statsmodels. However, they all serve specific purposes

### Data Sets

#### Weather Data

Can be found in `./data/weather_data.csv`

_NOTE:_ We are specifically interested in the Philadelphia Airport data

The weather data is free from NOAA (National Centers for Environmental Information) and can be found here: https://www.ncei.noaa.gov/

#### Energy Data

Can be found in `./data/residential_usage.csv`

This is energy data from a single family residential property in Southern New Jersey. Unfortunately it was quite difficult to find free anonymous multifamily data.

The energy data can be found here: https://data.mendeley.com/datasets/rfnp2d3kjp

#### Cleaned Data

The cleaned data is a combined version of the two datasets. CDD and HDD stand for Cooling Degree Days and Heating Degree Days respectively. These values are commonly used in energy calculations. Please reference this [weather.gov link](https://www.weather.gov/key/climate_heat_cool) for more information.