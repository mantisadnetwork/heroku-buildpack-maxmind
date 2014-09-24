# MaxMind Build Pack
Ensure your application has the latest copy of MaxMind data when deploying. Ideally, you should have a way to restart your application to make sure this build back happens often enough (if you deploy daily/weekly, you have nothing to worry about).

## How it Works
The database file(s) is saved to a Heroku cache directory that is persisted across builds. If the database file does not exist, or is older than a week, a new copy is downloaded and moved to your project before deployment. All database files are stored in the root of your project when deployed.

## Required Environment Variables
* MAXMIND_KEY = The license key they provided which allows you to download files.
* MAXMIND_EDITIONS = Comma delimited list of databases to download ie: "GeoIP2-ISP,GeoIP2-City,GeoIP2-Country"

## How to Use
Follow the instructions at https://github.com/ddollar/heroku-buildpack-multi for using multiple build packs. Simply add this repository to this list and wallah!

## TODO
* Find a way to query MaxMind if new data is available vs. using file time