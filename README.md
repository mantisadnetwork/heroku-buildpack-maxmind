# MaxMind Build Pack
Ensure your application has the latest copy of MaxMind data when deploying. Ideally, you should have a way to restart your application to make sure this build back happens often enough (if you deploy daily/weekly, you have nothing to worry about).

## How it Works
The database file(s) is saved to a Heroku cache directory that is persisted across builds. If the database file does not exist, or is older than a week, a new copy is downloaded and moved to your project before deployment.

## Required Environment Variables
* MAXMIND_KEY = The license key they provided which allows you to download files.
* MAXMIND_PATH = The path relative to the build directory where you want the file stored, ie: "GeoIP2-ISP.mmdb" or "path/to/folder/GeoIP2-ISP.mmdb"

## TODO
* Expand buildback to support mulltiple database files and locations
* Find a way to query MaxMind if new data is available vs. using file time