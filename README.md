WIRELESS DEBUGGING IN 5 MIN!
===============================

Wireless charging is very popular now-a-days. So, why not wireless debugging! 

The era of USB debugging is over (well, almost over :p). It’s an old trick and old is gold you know.
<br />Let’s fight:

<ol>
<li>Initializing the wireless debugging process:
..* Connect your device with PC using USB (opps).
..* Open cmd and run: `adb tcpip 5555`

`*If you see that **‘adb is not recognized as internal or external command’**, your adb is not set up globally. Set up adb globally by following the steps written in the bottom of this tutorial.`
</li>

2.  Get your device’s IP address:
..* Open cmd and run `adb shell netcfg` or `adb shell ifconfig`. From the result you will see a part with **wlan0**.  
..* Here you will see something like **inet addr:192.168……**. This is your **DEVICE_IP_ADDRESS**.

**To find the IP address while using OSX run the command `adb shell ip route`.**

3. Now connect: 
..* In cmd: `adb connect DEVICE_IP_ADDRESS:5555`

**That’s all!** You can now remove the USB and run the app from Android studio or any other way!

4. Disconnect:
After debugging done disconnect the device using: 
..* `adb -s DEVICE_IP_ADDRESS:5555`

WARNING: leaving the option enabled is dangerous. Anyone in your network can connect to your device in debug, even if you are in data network. Do it only when connected to a trusted Wi-Fi and remember to disconnect it when done!
</ol>


Set up adb(Android Debug Bridge) globally:
------------------------------------------
We need to set a path variable to use adb from anywhere.  Don’t be frightened or bored, it’s super easy. The adb is normally located here: 

Go to: Local Disk(C :) -> Users -> (Username) ->  AppData -> Local -> Android -> sdk -> platform-tools

-> Copy this folder’s path.
-> Now right click on (My Computer/This PC), select properties. 
-> A window will be opened with your PC’s basic info. 
-> From the left panel of this window select ‘Advanced system settings’.
-> Another dialog will be opened -> select ‘Advanced’ tab -> Click ‘Environment Varibales…’(at the bottom of the dialog)
-> Another dialog will be opened. From the upper part double click on ‘Path’.
-> In windows version <10 place a ‘;’ and paste the path here.
-> In windows version 10 click on ‘New’ and paste the path.
-> Now click on all three ‘ok’ buttons and we are done.
