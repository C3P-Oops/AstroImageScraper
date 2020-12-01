# AstroImageScraper
 Image retrieval tool for NASA APOD archive
 
 #### Goal:
 To build a tool to download images between dates to a folder so that I may use them on my desktop.
 
 ---
 Images I choose are from the Astronomy Picture of the Day Archive.
 https://apod.nasa.gov/apod/archivepix.html
 
 Format for each picture URL is https://apod.nasa.gov/apod/apYYMMDD.html where:
     YY is the 2-digit year
     MM is the 2-digit month, including leading zeros
     DD is the 2-digit date, including leading zeros
 
     200403 is the proper date format for the image on April 3rd, 2020
     URL for that date: https://apod.nasa.gov/apod/ap200403.html
 
 Pictures are labeled with some title associated. They are not named in a way to allow the automated retrieval by date.
 
 - Every page has only one picture on it, so inspecting the HTML source has the image URL in the IMG SRC tag.
 - URL for source:
         [Firefox](view-source:https://apod.nasa.gov/apod/apYYMMDD.html)
 - URL for image is:
         https://apod.nasa.gov/apod/<image/year/name.jpg>, where <> encloses the IMG SRC tag in the HTML
 
 Example:
         view-source:https://apod.nasa.gov/apod/ap200221.html
 
```
Pseudo:

Receive start date from user
Receive end from user in the following format
  d30 for 30 days       (input string starts with d)
  date for end date
Create string list of days between in YYMMDD format
Create string list of appended URLs
Navigate to appropriate date URL
Put HTML source through a BufferedReader
Search for "<IMG SRC=" in source
If found
  Collect the path name of the file
  Add to ArrayList<String>
Replace entries in ArrayList with appended URL
Retrieve file to user's chosen dir
```
