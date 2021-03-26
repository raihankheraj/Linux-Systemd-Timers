Weather-Service with Timer

---
Helpful weather service for users running *systemd* on Linux OS
---
Timer refreshes weather file every 60 mins for destination identified from host IP address
To use the service, you must configure the weather_script, weather_script.service, and weather_script.timer according to the following instructions:

Weather Script:
1. Create a bin folder in your `$HOME` directory if it does not already exist
   -`mkdir bin`
2. Place the weather_script file in the bin directory 
*running the script will create a weather file in the bin directory, which holds the weather data for the user*

Weather Service and Weather Timer:
*systemd init needed to run following commands*
1. Save the weather_script.service file and the weather_script.service file into your `$HOME` directory 
2. Copy the weather_script.service file and the weather_script.service file to /etc/systemd/system/
   -`sudo cp weather_script.service /etc/systemd/system/weather_script.service`
   -`sudo cp weather_script.timer /etc/systemd/system/weather_script.timer`
3. Reload system daemons 
   -`sudo systemctl daemon-reload`
4. Enable the timer to run on boot
   -`sudo systemctl enable --now weather_script.timer`
---
Congratulations! The service is now succesfully installed
