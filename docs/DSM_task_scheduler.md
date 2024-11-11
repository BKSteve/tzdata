Config the DSM Scheduler
====================================================

This is to get updated tzdata with RegionCity files into the right place.  
Copy the files `ZoneInfoDSM.sh` and `zonetimeinfo.zip` to a folder on your DSM.  

Edit the folder location in `ZoneInfoDSM.sh` to match where you saved the `zonetimeinfo.zip`.  
Then setup a DSM task schedule in `Task Scheduler` to execute the bash file to update the /usr/share/zoneinfo files.
1. Create the new `Scheduled Task` of `User-defined script` and 
2. Give it a name and set the user to `root`, uncheck `Enabled`
3. Got to `Task Settings` and in user script area put  
   ```/bin/bash /volume1/Media/script/ZoneInfoSC.sh > /volume1/Media/script/zoneinfo.log```  
   where */volume1/Media/script* is your folder as above.
4. OK and confirm with root password.
5. Select the new task and click run to execute.


Note: If you edit the script on Windows the script may fail.  
To fix this you need proper EOL configuration  
&nbsp;&nbsp;&nbsp;&nbsp;Open your shell file on NotePad++  
&nbsp;&nbsp;&nbsp;&nbsp;Click on Edit on Top bar menu, then choose EOL Conversion --> Unix(LF)  
&nbsp;&nbsp;&nbsp;&nbsp;Now copy this file in your Linux system and it should run without errors.  
