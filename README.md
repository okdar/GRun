# GRun
Configurable Garmin Watch datafield

![GRun Cover Image](/doc/GRunCover.png) 


## Description
Highly configurable datafield where you can select up to 10 fields to display. If less fields are configured, the field area on each line will automatically expand.
The second and third row display a header field with the value. The Header fields can be positioned Top/Top, Top/Bottom or Bottom/Top.

The first, fourth and fifth row display values without header.

The following fields are currently supported:
- Empty
- Time
- Timer
- Distance
- Current Heart Rate
- Average Heart Rate
- Current Pace
- Average Pace
- Current Speed
- Average Speed
- Current Cadence
- Average Cadence
- Calories
- Altitude
- Total Ascent
- Total Descent
- ETA 5K
- ETA 10K
- ETA Half Marathon (21.0975 km)
- ETA Marathon (42.195 km)
- ETA Lap
- Lap Count
- Previous Lap Time
- Lap Time
- Lap Distance
- Lap Pace
- Time Ahead/Behind
- Training Effect (on supported devices)
- Battery Icon
- GPS Icon
- GPS Icon and Battery Icon

High-Memory devices also supports the following fields:
- Heart Rate Zone
- Average Pace (Last X sec)
- Average Speed (Last X sec)
- Average Vertical Speed (m/min) (Last X sec)
- Average Vertical Speed (m/hour) (Last X sec)
- Current Power (on supported devices)
- Average Power (on supported devices)
- Max Power (on supported devices)
- Target Pace 5K
- Target Pace 10K
- Target Pace Half Marathon (21.0975 km)
- Target Pace Marathon (42.195 km)
- Target Pace Lap Distance
- Target Speed 5K
- Target Speed 10K
- Target Speed Half Marathon (21.0975 km)
- Target Speed Marathon (42.195 km)
- Target Speed Lap Distance

Training Effect is supported on the following devices:
- Descent Mk1
- Edge 1030
- Edge 1030 Bontrager
- Edge 520 Plus
- Edge 530
- Edge 830
- Fenix 5
- Fenix 5S
- Fenix 5X
- Fenix 5X Plus
- Fenix 6
- Fenix 6 Pro
- Fenix 6S
- Fenix 6S Pro
- Fenix 6X Pro
- Fenix Chronos
- Forerunner 245
- Forerunner 245 Music
- Forerunner 645
- Forerunner 645 Music
- Forerunner 935
- Forerunner 945
- MARQ Athlete
- MARQ Aviator
- MARQ Captain
- MARQ Driver
- MARQ Expedition

Power is supported on the following devices:
- D2 Charlie
- D2 Delta
- D2 Delta PX
- D2 Delta S
- Descent Mk1
- Edge 1030
- Edge 1030 Bontrager
- Edge 520 Plus
- Edge 530
- Edge 820
- Edge 830
- Fenix 5 Plus
- Fenix 5S Plus
- Fenix 5X
- Fenix 5X Plus
- Fenix 6 Pro
- Fenix 6S Pro
- Fenix 6X Pro
- Forerunner 945
- MARQ Athlete
- MARQ Aviator
- MARQ Captain
- MARQ Driver
- MARQ Expedition

List of High-Memory devices:
- D2 Charlie
- D2 Delta
- D2 Delta PX
- D2 Delta S
- Descent Mk1
- Edge 1030
- Edge 1030 Bontrager
- Edge 520 Plus
- Edge 530
- Edge 820
- Edge 830
- Edge Explore
- fenix 5 Plus
- fenix 5S Plus
- fenix 5X
- fenix 5X Plus
- fenix 6 Pro
- fenix 6S Pro
- fenix 6X Pro
- Forerunner 645 Music
- Forerunner 945
- MARQ Athlete
- MARQ Aviator
- MARQ Captain
- MARQ Driver
- MARQ Expedition
- Oregon 7xx
- Rino 7xx

## Notes
- Fields related to distance are displayed in km or mile depending on the user profile.
- Fields related to speed are displayed in km/h or mile/h depending on the user profile.
- Fields related to pace are displayed in min/km or min/mile depending on the user profile.
- Heart Rate is displayed in color based on user profile heart rate zone.
- Current Pace/Speed, Average Pace/Speed, Lap Pace, Target Pace (5k, 10k, etc.) and "Time Ahead/Behind" are displayed in color based on application parameters
  - Blue if too fast, Green if within Target Pace Range, Red if too slow

## Configuration
### Target Pace
"Target Pace" is your ideal pace for a run. The value is configured in seconds per km or in seconds per mile. km or mile is chosen automatically based on watch settings.
For example, if your watch is configured with metric values and your objective is to run 10k in exactly 1 hour, configure "Target Pace" to be 360 (360 seconds = 6:00 min/km).

### Pace Range
Pace Range is used to determine if your pace/speed is too slow or too fast. For example, if you configure "Target Pace" at 5:30 min/km (330 seconds) and you can configure "Pace Range" at 15 seconds, it means a good pace will be within 5:15 min/km to 5:45 min/km. If your pace/speed is too slow, the pace/speed is displayed in red, if it's too fast, it is displayed in blue and if it's within the range, it will be displayed in green.

![GRun PaceColor](/doc/GRunWatch5.png)


### Lap Distance (in meters)
Lap Distance is useful for people running in competition. It allows to readjust distance. For example, if you set the value to 1000 (meters), it allows you to press the lap button at each kilometer. If Garmin had calculated a value of 1.01 km at km #1, it will readjust to 1.00 km when you press the lap button. Average Speed, Pace, ETA, etc. will be readjusted using the updated distance. To determine what the new distance should be, the distance is divided by "Lap Distance" and is adjusted to the closest value. For example, if "Lap Distance" is set to 400 meters and you press the lap button at 1195 meters, the distance will be corrected to 1200 meters. If the distance was 1225 meters, it would also be corrected to 1200 meters. It is important to note that you do not have to press lap button on every lap since the value is always corrected using the closest lap distance.

__*** Note__ : Lap Distance must always be set in meters regarless of the watch settings. If you'd like to set the "Lap Distance" to 1 mile, you have to configure it to 1609 (1609 meters = 1 mile).

### Header Position
Header Position can have 3 positions.
#### 1) Top / Top
![GRun TopTop](/doc/GRunWatch2.png)
#### 2) Top / Bottom
![GRun TopBottom](/doc/GRunWatch3.png)
#### 3) Bottom / Top
![GRun BottomTop](/doc/GRunWatch4.png)

### Header Height
On row #2 and #3, header height can be configured using a percentage of the area.
You can hide headers by setting the value to 0:

![GRun Hide Headers](/doc/GRunHeaders0.png)

A value of 100 will hide the actual values (not very useful):

![GRun Hide Headers](/doc/GRunHeaders100.png)

Default value of 30 looks like this:

![GRun Hide Headers](/doc/GRunHeaders30.png)


### Column Width Ratio
"Column Width Ratio" is used to configured the width of each fields on row #2 and #3. You simply have to provide 3 numbers separated by comma. The default value is 2,1,2 meaning colum #1 and #3 are 2 times bigger than column number #2. For those who prefer percentage, similar result would have been achieved with "40,20,40" : column #1 and #3 taking 40% of the available width while column #2 taking 20%. If a parameter is set to "Empty", its percentage will be set to 0. If we keep the example of "2,1,2" with parameter #2 set to empty, value will automatically became "2,0,2". In this case, it will mean column #1 and #3 will take 50% of the screen.

Default value: "2,1,2" with middle parameter set to Empty on first row

![GRun MiddleColumn100](/doc/GRunWatch6.png)

Configuration using "1,1,1" with middle parameter set to Empty on first row
![GRun MiddleColumn125](/doc/GRunWatch7.png)
 
### Uniform Background Color
By default, rows 4 and 5 have a different background color.

![GRun BottomTop](/doc/GRunWatch10.png)

To have a uniform background color, simply enable this setting.

![GRun BottomTop](/doc/GRunWatch11.png)

### Dynamic Header Background Color
If enabled, background colors will changed depending on your pace/speed.

### Dynamic Data Foreground Color
If enabled, data foreground colors will changed depending on your pace/speed.

### Fields
Up to 10 fields can be displayed using application parameters.

![GRun GarminConnectParams](/doc/GarminConnectParams.png)
![GRun Fields](/doc/GRunWatchFields.png)

#### Less fields
If some fields are configured with option  **Empty**, the other fields on the same line will automatically expand. For example, the following screen is configured with **Field 2B = Empty**.

![GRun Expand](/doc/GRunWatch1.png)

#### Fields Description
Most of the fields do not required explanation, but others might...

##### ETA (5K, 10K, Half Marathon, Marathon, Lap Distance)
ETA fields help determine your finish time based on your average speed/pace. It can help determine the finish time for 5 km, 10 km, half-marathon (21.0975 km) a marathon (42.195) or the "Lap Distance" configured on the "Lap Distance" parameters.

##### Time Ahead/Behind
Use this field to determine how far you are from your "Target Pace". For example, if your "Target Pace" is configured to 360 (6:00 minutes/km) and you have run 3 km in 28 minutes and 30 seconds, the field will display "-1:30" since you are 1 min and 30 seconds faster than planned.

##### Training Effect
You can read more about training effect @ https://www.garmin.com.my/minisite/runningscience/#training-effect

##### Average Speed/Pace (Last X sec)
You can use this metric if you'd like more control over the calculated speed. This field calculates the speed/pace of the last X seconds by calculating the distance run during those last seconds. You configure the number of seconds you'd like to use using the field "Speed/Pace (Last X sec)".

##### Average Vertical Speed (/min)
Calculate the vertical speed in meter/min or feet/min depending on the watch settings. This field calculates the vertical speed of the last X seconds by calculating the altitude difference between now and the previous X seconds. You configure the number of seconds you'd like to use using the field "Vertical Speed (Last X sec)".

##### Target Pace/Speed (5K, 10K, Half Marathon, Marathon, Lap Distance)
This field is helpful to determine the pace/speed required to finish your race at "Target Pace". For example, if your "Target Pace" is configured to 360 (6:00 minutes/km) and you have run 3 km in 15 minutes, "Target Pace 5K" will display "7:30" since you still have 15 minutes to run 2 km.


## Release Notes
### Version 1.25
 - Added "Required pace to meet Target Pace" for 5K, 10K, Half Marathon and Marathon distance
 - Replaced option for "Dynamic Data Color". Data Color can now be more customized

Memory Usage on va3   (Current | Peak) : 
   * At startup:           25.4 kB | 27.0 kB
   * 10 sec running:       25.4 kB | 27.3 kB
   * After setting change: 25.4 kB | 28.2 kB

### Version 1.24
 - Bugfix on Garmin Venue to properly display fields

Memory Usage on va3   (Current | Peak) : 
   * At startup:           25.6 kB | 27.0 kB
   * 10 sec running:       25.6 kB | 27.4 kB
   * After setting change: 25.6 kB | 28.4 kB

Memory Usage on fr945 (Current | Peak) : 
   * At startup:           31.5 kB | 33.4 kB
   * 10 sec running:       31.5 kB | 33.7 kB
   * After setting change: 31.5 kB | 34.5 kB

### Version 1.23
 - Replaced "Min Pace", "Max Pace" settings with "Target Pace" and "Pace Range"
 - Reorder settings
 - Added color for speed metrics (current, average)
 - Removed the following fields on all supported devices:
   + Total Corrected Distance
 - Added the following fields on all supported devices:
   + Time Ahead/Behind
   + Average Cadence
 - Added the following fields on high-memory devices:
   + Current Power
   + Average Power
   + Max Power
   + Average Speed/Pace over a defined period of time
   + Average Vertical Speed over a defined period of time (in meter or feet per minute)
   + Average Vertical Speed over a defined period of time (in meter or feet per hour)
   + HR Zone Number
   + Target Pace/Speed (5K, 10K, Half Marathon, Marathon, Lap Distance)

Memory Usage on va3   (Current | Peak) : 
   * At startup:           25.5 kB | 27.0 kB
   * 10 sec running:       25.5 kB | 27.4 kB
   * After setting change: 25.5 kB | 28.4 kB

Memory Usage on fr945 (Current | Peak) : 
   * At startup:           31.5 kB | 33.4 kB
   * 10 sec running:       31.5 kB | 33.7 kB
   * After setting change: 31.5 kB | 34.5 kB
   
### Version 1.22
 - BugFix : It it now possible to use "Lap Time" if "Lap Distance" is set to 0
 - Compiled using Connect IQ SDK Release 3.1.6

### Version 1.21
 - Removed "Average Pace (Calculated manually using timer/distance)" field
 - Replaced field "Time spend on current km/mile" by "ETA Lap"
 - Replaced field "Time spend on previous km/mile" by "Previous Lap Time"
 - Added field "Lap Count" 
 - Increased line width between fields from 1 pixel to 2 pixels


 - Memory Usage on va3 (Current | Peak) : 
   * At startup:           25.6 kB | 27.0 kB
   * 10 sec running:       25.6 kB | 27.4 kB
   * After setting change: 25.6 kB | 28.4 kB
 
 - Compiled using Connect IQ SDK Release 3.1.5
 
### Version 1.20
 - Added a parameter to have a uniform background color. By default rows 4 and 5 have a different background color.
 - Added support for new watches (Descent Mk1, Edge 530, Edge 820, Edge 830, Fenix 6, Fenix 6 Pro, Fenix 6S, Fenix 6S Pro, Fenix 6x Pro, Forerunner 245, Forerunner 245m, Forerunner 945, Captain Marvel, First Avenger, MARQ Athlete, MARQ Aviator, MARQ Captain, MARQ Driver, MARQ Expedition, Oregon 7xx, Rino 7xx, Venu, Vivoactive 3d, Vivoactive 3m LTE, Vivoactive 4, Vivoactive 4S)

### Version 1.19
 - Redesign settings to adjust column width (Less user friend, but more customizable).
   + Default value is "2,1,2" which means first column will have a width of 2/5, second column will have a width of 1/5 and third column will have a width of 2/5. If a parameter is set to Empty, the value is ignored. For example, if column2 is empty, that the ratio become 2/4 for column #1 and 2/4, 0/4 for column #2 and 2/4 for column #3.
 - Add a parameter to set "Header Height" in percentage. This allow to completely hide headers to maximize space.
 - Header Font tried to used the maximum space possible
 - Changed default parameters

### Version 1.18
 - Added Training Effect on supported devices (Fenix 5, Fenix 5s, Fenix 5x, Fenix 5x Plus, Fenix Chronos, Forerunnner 645, Forerunnner 645 Music, Forerunnner 935, Edge 1030, Edge 520 Plus)
 - Add a parameter to correct distance on lap. Distance is rounded to the nearest "Lap Distance".
 - Code improvement to optimize memory
 - Code Framework using Jungles to implement features for specific devices (Example: Training Effect)

### Version 1.17
 - Added options to display Header background or data foreground in color
 - Area 4a/4b and 5 can be shrinked together if one of them is empty
 - Improve code to use less memory

![GRun Version 1.16](/doc/GRunWatch9.png)

### Version 1.15
 - Added color for Lap Pace

### Version 1.14
 - Added the following fields: Lap Time, Lap Distance, Lap Pace
 
### Version 1.13
 - Adjust font vertical position for fenix 5s and fenix chronos

### Version 1.11
 - Area 4 and 6 expand vertically: If values 4A/4B or 5 are missing, area 4A/4B or 5 will expand vertically
 - ETA Auto-Switch: If one area is configured with "ETA 5K" and you reach 5 km during your run. the value will automatically change to "ETA 10K", then "ETA 21K", then "ETA 42K". Same apply to "ETA 10K" and "ETA 21K".
 - "Time spend on current km/mile" displays a background color indicating progress on the current km/mile.
 - Float fields are displayed with 2 digits if lower than 10 (Example: 9.92). Values greather than 10 display a single digit (Example: 10.1)
 - Bug Fix: Area "Battery Icon" now display the battery icon instead of the GPS icon
 - Code Optimization to minimize memory usage
 
 ![GRun Version 1.10](/doc/GRunWatch8.png)
