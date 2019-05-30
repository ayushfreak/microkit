# Micro Kit

Micro Kit is a Python Package for dealing with API Response and Logging related tasks.


## Helper Classes provided in MicroKit!

  - Custom Response Class
  - Custom File Logger Class

##  Custom Response Class
Provides the developer with a predefined schema (As Shown Below) of response object along with all the built-in features of the Flask Response Class

- Sample Response Object Schema:
```json
{
    "message": " ",
    "data": {
            },
    "status code": 
}
```
  - Header(default)
```json
{
  "content-type": "application/json"
}
```
### Features and Constraints

  - If data is in string format it is considered as a message and data key is left empty.
  - Data can be either a Python Dictionary or a Python List.
  - In case of a Python list an additional data key is introduced assuring data is in dictionary format.
  - All named arguments provided by the flask response class can be passed here.


### Installation

Micro Kit requires [Python](https://python.org/) v2.7 to run.
Use the package manager [pip](https://pip.pypa.io/en/stable/) to install microkit.


```sh
$ pip install microkit
```
### Usage

```python
from microkit import CustomResponse

CustomResponse(data, status_code, message, **kwargs)
```
- Default Params
```python
CustomResponse(data, status_code=200, message="OK", **kwargs)
```

##  Custom Logger Class
A logger class to maintain a common logging format(User Defined) across the API along with allowing the developer to use it without having to write the logger module.

- Sample Logging Format:
```
'[%(asctime)s - %(name)s - %(levelname)s - %(module)s - %(funcName)s() - %(lineno)d] - %(message)s'
```
- TimeStamp Format(FIXED):
 ```json
 "%Y-%m-%d %H:%M:%S"
```

### Features 

  - Maintains a common Logging Format across the API
  - Give the flexibility to c
  - Save developer's time to write the Logger Module

### Installation

Micro Kit requires [Python](https://python.org/) v2.7 to run.
Use the package manager [pip](https://pip.pypa.io/en/stable/) to install microkit.


```sh
$ pip install microkit
```
## Usage

```python
from microkit import FileLogger

FileLogger(api_name, absolute_log_file_path, log_format, logging_level)
```
- Default Params
```python
FileLogger(api_name, absolute_log_file_path, log_format=None, logging_level=DEBUG)
```
- Note: All the logging levels can be set via FileLogger.LEVEL (FileLogger.DEBUG)

License
----

GNU General Public License