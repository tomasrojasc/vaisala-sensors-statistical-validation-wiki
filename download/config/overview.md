# download.config

This file is very important for the downlad to properly work when using sftp. 

In order to work you will need a `config.py` file located at `download/config.py` with the following 
python variables:

* `server`: `str` variable containing the name of the server, in this case is `"people.sc.eso.org"`
* `username`: `str` variable corresponging to the user to log into
* `password`: `str` variable corresponging to the password to the user
* `port`: `int` variable in this case equal to  `22222`