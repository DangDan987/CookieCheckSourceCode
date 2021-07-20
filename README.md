# CookieCheck - forked

Here you find the forked version of the CookieCheck tool (https://github.com/CookieChecker/CookieCheckSourceCode).
It is a simple Python script that instruments a test using Google Chrome,
and matches the resulting cookies against a list of well-known trackers.

As of 2021, I have made updates to the script that allow one to work through a list of websites, allowing for bulk analysis.
Be aware that time-outs may be a concern if the list contains more than 1000 sites.

## Prerequisites
You must have installed an updated version Google Chrome and Python3.
We tested this software on Ubuntu.
Few Python3 packages are needed: `requests`, `websocket-client`, and `file input`.
You can install them using the `pip3` command-line tool.

## Usage (multiple sites)
To test against multiple websites, create a flat file list of URLs (each URL on a separate line). Update the "Filepath" variable in the script to point to your list. After saving your changes, then run the tool as in the following example:
```
./modformultiple_test_site_native.py
```
## Usage (single site)
To test if a Web site installs cookies, run the tool specifying the target Web site as argument, like in the following example:
```
./test_site_native.py www.google.com
```

The tool provides a JSON object on the standard output, with the results of the test.
It is a dictionary containing three entries:
* `trackers_cookies` contains the cookies set by the list of trackers contained in the file `trackers_ghostery_disconnect`
* `other_cookies` contains the cookies set by other third parties
* `trackers_no_cookies` contains the trackers contacted without a cookie exchange.

