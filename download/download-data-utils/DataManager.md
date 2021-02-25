# DataManager

## __class DataManager(i_date, f_date)__

class for downloading data from sftp server

__Important:__

In order for this to work you will need to create a `config` file in `download/config.py`. To read more about this, click [here](download/config/overview)


### Parameters

__i_date__
> date `str` formated as `dd-mm-yyy` marking the begining of the range of data to download we are interested on

__f_date__
> date `str` formated as `dd-mm-yyy` marking the end of the range of data to download we are interested on


### Examples

Downloading data from `20-12-2020` to `02-01-2021`
```python
r = DataManager("20-12-2020", "02-01-2021")
r.connect()
r.get("./data_folder")
r.close()
```

### Attributes

__i_date__
> date `str` formated as `dd-mm-yyy` marking the begining of the range of data to download we are interested on

__f_date__
> date `str` formated as `dd-mm-yyy` marking the end of the range of data to download we are interested on

__sftp__
> [`paramiko.SFTPClient`](http://docs.paramiko.org/en/stable/api/sftp.html) object (after connection)

__transport__
> [`paramiko.Transport`](http://docs.paramiko.org/en/stable/api/transport.html) object (after connection)


### Methods

__connect()__ 
> This method establishes a connection betwen the local and the server

__get(path)__
> This method downloads all the data for which the date is between i_date and f_date, excluding f_date

__close()__
> Closes the sftp connection