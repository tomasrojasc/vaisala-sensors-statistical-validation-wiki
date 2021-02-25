# Downloading old data

This page has a review on the file `download_old_data.py` present in the main folder of the project

## Overview

In this filo a funtion alled `download_old` can be found, this funtion is in charge of downloading all tha data for a 
given day, we then call that function multiple times via a `multiprocessing.Pool` objet to be able to paralelize the process. Is important
to note that the fat that this is done via this funtion does not mean that that is neessarly the way to go, if your goal is just to have one csv 
with multiple meassurements then chech the page for the [`download.download_old_data`](download/module) 


## See also
* [`download.download_old_data`](download/module) 