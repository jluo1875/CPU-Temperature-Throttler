# CPU Throttler

Script for throttling system CPU frequency when getting hot based on your desired maximum temperature (celsius).

If the maximum temperature you set is exceeded, the script will limit the speed of all your CPU cores until the system is below your desired maximum temperature. If your system remains above maximum temperature after completely limiting your CPU cores, it will simply stay limited until temperatures drop below the maximum set.

When you exit or kill the script, the limitation is automatically released and cpu can run at maximum speed again.

# How to Use
```
cpu_throttle.py [-h] [--time TIME] [--crit_temp CRIT_TEMP] [--debug]

optional arguments:
  -h, --help              show this help message and exit
  --time TIME             Seconds to cooldown cpu before next check, default is 30 seconds.
  --crit_temp CRIT_TEMP   Temp for cpu to throttle down (temperature in celcius degrees).
                          Default is 64 degrees.
  --debug                 Output more information when set to True.

Example: sudo cpu_throttle.py --crit_temp 45 --time 15 --debug
```
This will keep cpu temp below 45 degrees celcius (most of the time) and let cpu cool down
at a lower speed for 15 seconds, before checking again. Also it prints all debug messages to screen (and to logfile).


Stress test cpu with command:
```
stress -c 4 -t 120s
```
With c the number of threads and t time in seconds to stress test.

# Dependencies
This script needs package:
```
cpufrequtils
```
Install using:
```
sudo apt install cpufrequtils
```


