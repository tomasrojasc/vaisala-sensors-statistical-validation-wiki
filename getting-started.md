# Getting Started

In this page you will be able to find all that is needed to get the project up and running.

## First steps

the first thing to do is to create a virtual environment. At the moment we are going to use virtualenv.
Assuming you have virtualenv installed (if not installed you can read about 
installation [here](https://virtualenv.pypa.io/en/latest/installation.html))

In case you are using conda, please read [using conda](#using-conda)

To create the virtual environment simply type the following command in your terminal:

```bash
virtualenv myvenv
```

you can install it wherever you like, and change `myvenv` for whatever name you like.

Once installed you will need to install the dependencies, for that, first you need to activate the environment with:
```bash
source myvenv/bin/activate
```

then to install the requirements go to the repository folder (if not there yet) and type:
```bash
pip install -r requirements.txt
```

#### Config file
in order to this module to work you will need a `config.py` file located at `download/config.py` with the following 
python variables:
* `server`: `str` variable containing the name of the server, in this case is `"people.sc.eso.org"`
* `username`: `str` variable corresponging to the user to log into
* `password`: `str` variable corresponging to the password to the user
* `port`: `int` variable in this case equal to  `22222`

with this you should be all set and ready for the downloading and processign of the data


## Downloading and processing the data

In order to download and process the data to have light and easy-to-read csv files, 
you will have to execute the following command in your terminal

```bash
bash update_Data.sh XXXX/bin/activate
```

where `XXXX` is the path to you virtual environment.

If you want to know more about the bash file, visit [this page](bash-file)

Once that command is finished, you will find in `processed_data/csvs` 
six files: `old_data.csv`, `asmvai1.csv`, `asmvai2.csv`, `asmvai3.csv`, `asmvai4.csv` and `asmvai5.csv` 
containing all the data available from `2020-11-10` until the day before the command was executed.
The first file correspond to the data from the old sensors, while the other files correspond to the 
data from all different five new stations.


#### Notes
* The time it takes to download and process the data the first time may be significant, 
depending on the characteristics of your cpu and the number of threads is able to handle. As a reference, with date
`2021-01-21` it took __3.5 hours__ with __20 threads__


* There is currently no automated support for virtual environments created with conda, at least by now is only 
supported virtualenv, though it is one of the considerations to fix since part of the team uses conda. For now, 
read [using conda](#using-conda).

#### Using conda

To use a conda environment, first create your new environment with

```bash
conda create --name myvenv --file requirements.txt
```

##### ~~Using conda with update_data.sh~~ Downloading data manually with conda
Since there is no way to download the data in an automated way when using conda, 
the following scripts will need to be run in order to have the data:

* `download_old_data.py`
* `download_data.py`
* `data_processing.py`
* `make_csvs.py`
* `data_for_plots.py`

all this should be run from the project folder
