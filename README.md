# POLA-02_Analysis

This git page has been created to perform some analyses (plots,...) on the POLA-02 data. It is still under construction.

First you need Anaconda2 to perform analysis, especially jupyter notebook. Follow the following instructions to set up Anaconda and the relevant packages.

## Anaconda setup

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

## Analysis on the Extreme Energy Events (EEE)  data

- You can download the data from the website https://iatw.cnaf.infn.it/eee/monitor/dqmreport2/POLA-02/?C=M;O=D
- You will be prompted for a username and password. Please ask Farid or Eirik.
- As a start, you can download one daily data set and play with it.
- To download all the data from the beginning (since the detector started to run), run the "download_all.py" on your terminal and choose your favorite destination folder to store the data.
- The data files are in .csv format which can be read for example in Excel.
- There are three different types of data files which end with "summary_Trending.csv", "summary_Header.csv" and "summary_Weather.csv". Details on the different physical variables recorded by the detector will be available later.
- In the folder "Analysis_Example" you will find an example notebook which contains histograms and plots.