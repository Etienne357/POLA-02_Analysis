# POLA-02_Analysis

This git page has been created to perform analyses using data from the POLA detectors.

Start cloning the git repository
```
git clone https://github.com/Etienne357/POLA-02_Analysis.git
```
## Downloadind data files
Downloading the data files (may take some time) can be done by using the script `download_all.py`. First you should define the directory where you want to save the data files (the last line of the script). When run, the script asks you which type of file you'd like to download (csv, root or both). They contain the same information, but in different formats (see below). 

In order to download all the data from all three of the POLA detectors simply change the URL (on line 34 in `download_all.py`) to contain `POLA-01`, `POLA-02` or `POLA-03` and run the script again. Remember to change the output directory so that you put the data from the various detectors in different folders. For the script to work you will need to have wget which can be installed by doing `pip install wget`

## Analysing data 
You can read in ROOT files in python without having to install ROOT using the [uproot package](https://github.com/scikit-hep/uproot). For csv files there are alredy built-in functions in python to convert directly to e.g. pandas ([pandas.read_csv](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_csv.html)). Please look at the following two notebooks on how to read in ROOT or csv files into data frames in python, respectively

* Analysis_Example/test_Polar_csv.ipynb
* Analysis_Example/test_Polar_uproot.ipynb

For the latter you would need to install `uproot`. If you like to use ROOT you can use the complete example provided in 

* Analysis_Example/RootAnaExample.py

This script can be run by simply writing `python -i RootAnaExample.py <directory containing data>`. See further comments inline for more details. 

The variables available are listed in `Analysis_Example/variables_description.pdf`

## Software setup

If you want you can do the analysis in a jupyter notebook. Either install it stand-alone or follow the instructions below to set up Anaconda and the relevant packages. `Uproot` can be installed through pip indstall (see README file of [uproot package](https://github.com/scikit-hep/uproot)). You can also do the analysis using the ROOT package.

### Anaconda setup

1. Download Anaconda for linux from [https://repo.anaconda.com/archive/Anaconda2-2018.12-Linux-x86_64.sh](https://www.anaconda.com/download/)
2. Following the installation instructions at [http://docs.anaconda.com/anaconda/install/linux/](http://docs.anaconda.com/anaconda/install/linux/)
   - it should be done by simply doing `bash ~/Downloads/Anaconda2-2018.12-Linux-x86_64.sh` (assuming you downloaded anaconda to the Download directory of your Home folder) and follow the instructions
      - answer "YES" on the agreement
      - use the default location to install anaconda (or change the path to something else)
      - installation should then start
      - at the end you have to choose if you want the anaconda path to be put in your .bashrc file (YES: means that any new shell you open will have anaconda, NO: you will need to add the anaconda path to your PATH environment variable whenever you like to use anaconda)
3. First do some initialization of the setup
   - To use the conda binary packages from the NLeSC Anaconda Cloud repository, you need to add the appropriate NLeSC main channel: `conda config --add channels https://conda.anaconda.org/NLeSC`
4. Create an environment as follows: 
   - `conda create -n name_of_environment`
5. Activate the environment: `conda activate name_of_environment`
6. Install the following packages in your working environment:
   - `conda install -c conda-forge uproot`. This package allows you to read allows you to read a ROOT file into an "easy to understand" panda framework.
   - `conda install -c conda-forge jupyterlab`
   - `conda install -c anaconda pandas`
   - `conda install -c anaconda h5py`
   - `conda install -c conda-forge matplotlib`
   - `conda install -c conda-forge anaconda scikit-learn`. This package allows you to apply some basic machine learning on the data. An example of a simple regression will be given later.
7. Now try running `jupyter notebook` in your conda environment.
