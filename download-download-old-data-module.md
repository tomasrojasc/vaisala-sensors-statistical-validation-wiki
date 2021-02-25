# Download old data module

The most important part of this module is the `RequestData` objet who is in charge of making requests.
This object is based on the `requests` library

## RequestData

__class RequestData(i_date, f_date)__
class for downloading data from online form

__Parameters:__
__i_date__
> date `str` formated as `dd-mm-yyy` marking the begining of the range of data to download we are interested on

__f_date__
> date `str` formated as `dd-mm-yyy` marking the end of the range of data to download we are interested on


### Examples

Downloading data from `20-12-2020` to `02-01-2021`
```python
r = RequestData("20-12-2020", "02-01-2021")
r.get()
```

saving the data to a file in a path

```python
r.save_csv("./data_folder", "data.csv)
```

### Attributes

__payload__
> dictionary containing the form

__url__
> url to the form

__i_date__
> date `str` formated as `dd-mm-yyy` marking the begining of the range of data to download we are interested on

__f_date__
> date `str` formated as `dd-mm-yyy` marking the end of the range of data to download we are interested on

__csv__
> variable to store the response csv from the form


### Methods

__get()__ 
> This method is in charge of actually making the request and saing the response in the __csv__ attribute

__save_csv(path, name)___
> method to save the csv file with tha given name in the given path


