# synology-vpn-reconnect

Initial script by: https://gist.github.com/GamerGun/0c82142f434178867c1de0cbd29622a4

Added two lines for default gateway modification.

Use this guide to install the script: https://blog.harrier.us/reconnecting-a-failed-vpn-connection-on-synology-dsm-6

Short instruction: 

Open the Control Panel and navigate to System > Task Scheduler. Under Create > Scheduled Task, click User-defined script. This will open up a Create task window.

On the General tab, name the task something like Reconnect VPN for easy identification. Make sure the task is running as root and that the Enabled box is selected.

On the Schedule tab, make sure the Date option is set to Run on the following days: Daily. To schedule the script to run every 5 minutes, set the Frequency to Every 5 minute(s). Note that by default, the script will only run for the first 55 minutes of the day (00:00 to 00:55). To ensure the script will run every 5 minutes for the entire day, change the Last run time to 23:55.

On the Task Settings tab, enable Send run details by email and enter your email address in the Email box. I would recommend enabling the Send run details only when the script terminates abnormally option. The script was written using different exit codes, allowing it to work well with this option. If you do not enable this option, you will receive an email every time the script runs, whether there is an error or not.

On the bottom of the Task Settings tab, paste the entire script into the User-defined script box.

Finally, click the OK button to close the Create task window and then click the Save button to save the changes to the Task Scheduler.
