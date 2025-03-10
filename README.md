# SunTide v3.0.0
A script to generate .csv files with data containing day-by-day tide predictions and daylight information for a given year. :sunny: :ocean:  


### The Suntimes CSV
Contains information such as sunrise and sunset times for every day in the year.
One row per day. The column headers are as follows:  
  
*DAY, MONTH, DATE, SUNRISE, SUNSET, DUR, DIFF, MORE/LESS*  
- Day - The abbreviated name of the weekday  
- Month - The name of the month  
- Date - The day of the month  
- Sunrise - The time of sunrise (HH:MM)  
- Sunset - The time of sunset (HH:MM)  
- Dur - The amount of daylight (hrs:mins)  
- Diff - The change in daylight from yesterday (hrs:mins:secs)
- More/Less - If the change was positive or negative  
  
> [!WARNING]
> Currently the sunrise and sunset times do NOT account for Daylight savings time. This is a work in progress.

### The Tides CSV
Contains information such as tide height for every day in the year.
One row per tide (so a day can have multiple rows). The column headers are as follows:  
  
*DATE, DAY, TYPE, HEIGHT, TIME*  
- Date - The date (mm-dd)  
- Day - The abbreviated name of the weekday  
- Type - If the tide is low or high  
- Height - The height of the tide in feet  
- Time - The time of the tide (HH:MM)  

If the program is told to get tides for multiple locations, the headers will be arranged horizonally, and a number added as a suffix to each column. For example, if two locations are specified, the headers will be:  
DATE1, DAY1, TYPE1, HEIGHT1, TIME1, DATE2, DAY2, TYPE2, HEIGHT2, TIME2  
Headers with suffix 1 in this example would corrospond to the first location given, and headers with suffix 2 to the second location.  
> [!NOTE]
> Tide predictions are generated by the National Oceanic and Atmospheric Administration, and retrieved from thier [API](https://api.tidesandcurrents.noaa.gov/api/prod/)

### Adjusting Settings
There are currently three settings:  
- Year - The year to pull the data for  
- Sun Location - The location to use to generate sunrise and sunset times in latitude/longitude coordinates  
- Tide Locations - A list of NOAA station ID's. These are seven digit ID numbers that correspond to locations around the US that have a station that records and predicts tide data.  
  
These settings are stored as global constants in settings.py. A simple text editor is enought to change these, just make sure there are no typos, as error checking is not very robust at the moment. :wink:

> [!CAUTION]
> There is no guarantee that the information generated by this program will be accurate.

## Coming Soon (Hopefully!)
- [ ] Account for Daylight Savings Time in sun times
- [ ] Allow ability to run for either sun or tides (not force you to run both)
- [ ] Allow for multiple locations for sun times
