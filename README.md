# POLA-02_Analysis

This git page has been created to perform analyses using data from the POLA detectors.

Start cloning the git repository
```
git clone https://github.com/Etienne357/POLA-02_Analysis.git
```
## Downloadind data files
Start with downloading the data files (this may take some time) by simply doing 
```
python download_all.py
```
Remember to define the directory where you want to save the data files (last line of the script). The script asks you which type of file you like to download (csv, root or both). They contain the same information, but in different formats (see below). In order to download all the data from all three of the POLA detectors simply change the URL (on line 34) to contain `POLA-01`, `POLA-02` or `POLA-03` and run the script again. Remember to change the output directory so that you put the data from the various detectors in different folders. For the script to work you will need to have wget, installed by doing `pip install wget`

## Analysing data 
You can read in the ROOT files in python using [uproot](https://github.com/scikit-hep/uproot), without having to install ROOT. For CSV files there are alredy built-in functions in python to convert directly CSV to e.g. pandas ([pandas.read_csv](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_csv.html)). Please look at the following two notebooks on how to read in ROOT or CSV files into data frames in python (means: no ROOT needed), respectively

* Analysis_Example/test_Polar_csv.ipynb
* Analysis_Example/test_Polar_uproot.ipynb

For the latter you would need to install `uproot`. If you like to use ROOT you can use the complete example provided in 

* Analysis_Example/RootAnaExample.py

This script can be run by simply writing `python -i RootAnaExample.py <directory containing data>`. See further comments inline. 

## Software setup

If you want you can do the analysis in jupyter notebook. Either install it stand-alone or follow the instructions below to set up Anaconda and the relevant packages. `Uproot` can be installed through pip indstall (see README file of [uproot package](https://github.com/scikit-hep/uproot)). You can also do the analysis using the ROOT package.

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

## Analysis on the Extreme Energy Events (EEE)  data

- You can download the data from the website https://iatw.cnaf.infn.it/eee/monitor/dqmreport2/POLA-02/?C=M;O=D. You will be prompted for a username and password. Please consult Farid or Eirik.
- As a start, you can download one daily data set and play with it.
- The data files are in .csv or .root format which can be read using pandas in jupyter notebook. The csv format is recommended since it does not require ROOT dependencies. Details on how to read the root and csv files are given in the "Analysis_example" folder.  
- To download all the data in csv or rot format from the beginning (since the detector started to run), run the "download_all_csv.py" or "download_all_csv.py" on your terminal.
-- You should change the download destination folder from the script in the wget function
-- Inside the script, you can modify folder_list1 to accomodate the latest data sets.
-- You need the wget module to download files in Python. Do `pip install wget`
- In the folder "Analysis_Example" you will find an example notebook which contains some plots.
- Details on the different physical variables recorded by the detector will be available soon.
