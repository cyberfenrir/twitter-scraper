## Pre- Requisites
- Basic knowledge on how to use a terminal/cmd
- **WEBDRIVERS**
    - If using Chrome, install ChromeDriver's latest version on the Chrome.
    - If using Safari, version 10+ with 'Allow Remote Automation' option enabled in Safari's Develop menu to control Safari via WebDriver. 
- python3
  - to check, in your terminal, enter `python3`
- pip or pip3
  - to check, in your terminal, enter `pip` or `pip3`
- selenium (3.0.1)
  - `pip3 install selenium`
- tweepy (3.5.0)
  - `pip3 install tweepy`
## Running the scraper
- open up `scrape.py` and edit the user, start, and end variables (and save the file)
-  ```python
    # edit these three variables
    user = '____USERNAME HERE____'
    start = datetime.datetime(2018, 12, 19)  # year, month, day
    end = datetime.datetime(2018, 12, 22)  # year, month, day
    ```   
- run `python3 scrape.py`
- once it's done, it outputs all the tweet ids it found into `all_ids.json`
- every time you run the scraper with different dates, it will add the new ids to the same file
  - it automatically removes duplicates

## Troubleshooting the scraper

- did you get a `no such file` error? you need to cd to the directory of `scrape.py`
- did you get a driver error when you try and run the script?
  - open `scrape.py` and change the driver to use Chrome() or Firefox()
- does it seem like it's not collecting tweets for days that have tweets?
  - open `scrape.py` and change the delay variable to 2 or 3

## Getting the metadata

- first you'll need to get twitter API keys
  - sign up for a developer account here https://dev.twitter.com/
  - get your keys here: https://apps.twitter.com/
  - enable Read and Write operation for the access tokens and keys (Optional)
- put your keys into the `api_keys.json` file
- open up `get_metadata.py` and edit the user variable (and save the file)
    ```python
    user = '____USERNAME HERE____'
    ```   
- run `python3 get_metadata.py`
- this will get metadata for every tweet id in `all_ids.json`
- it will create 4 files
  - `username.json` (master file with all metadata)
  - `username.zip` (a zipped file of the master file with all metadata)
  - `username_short.json` (smaller master file with relevant metadata fields - with less number of fields)
  - `username.csv` (csv version of the smaller master file)

## Warning
| Be careful while running the selenium scraping script repeatedly on Twitter might temporarily ban your account ! |
| --- |
