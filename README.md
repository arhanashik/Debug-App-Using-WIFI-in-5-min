Wireless Debugging in 5 Min!
===============================

Wireless charging is very popular now-a-days. So, why not wireless debugging! 

The era of USB debugging is over (well, almost over :p). It’s an old trick and old is gold you know.
<br />Let’s fight:
<br />
1. **Initializing the wireless debugging process:**
	<ul>
		<li>Connect your device with PC using USB (opps)</li>
		<li>Open cmd and run: <b>adb tcpip 5555</b></li>
	</ul>
	
	If you see that **adb is not recognized as internal or external command**, your adb is not set up globally. Set up adb globally by following the steps written in the bottom of this tutorial.

2. **Get your device’s IP address:**
	<ul>
		<li>Open cmd and run <b>adb shell netcfg</b> or <b>adb shell ifconfig(android version with 6.0 or higher)</b></li>
		<li>From the result you will see a part with <b>wlan0</b></li>
		<li>Here you will see something like <b>inet addr:192.168……</b>. This is your <b>DEVICE_IP_ADDRESS</b></li>
	</ul>
	
	To find the IP address while using OSX run the command **adb shell ip route**

3. **Now connect:**
	<ul style="list-style-type:disc">
		<li>In cmd: <b>adb connect DEVICE_IP_ADDRESS:5555</b></li>
	</ul>
	
	**That’s all!** You can now remove the USB and run the app from Android studio or any other way!
	
	**For connecting more than one device (this one is actuallity more usefull though :p)**
	<ul style="list-style-type:disc">
		<li>Disconnect any previous connection by following step 4</li>
		<li>Restart the adb server by <b>adb tcpip 5555</b></li>
		<li> Connect a device with USB and find the ip using step 2</li>
		<li>In cmd: <b>adb -d connect DEVICE_IP_ADDRESS:5555</b></li>
		<li>Device connected! Remove the USB and connect the next device with USB, find the ip and connect using <b>adb -d connect DEVICE_IP_ADDRESS:5555</b></li>
		<li>Connect as much as device you want. Fun right!!</li>
	</ul>

4. **Disconnect:**
	<br />After debugging done disconnect the device using:
	<ul style="list-style-type:disc">
		<li>In cmd: <b>adb disconnect DEVICE_IP_ADDRESS:5555</b></li>
	</ul>
	
	**WARNING:** leaving the option enabled is dangerous. Anyone in your network can connect to your device in debug, even if you are in data network. Do it only when connected to a trusted Wi-Fi and remember to disconnect it when done!


Set up adb(Android Debug Bridge) globally:
------------------------------------------
We need to set a path variable to use adb from anywhere.  Don’t be frightened or bored, it’s super easy. The adb is normally located here: 

Go to: Local Disk(C :) -> Users -> (Username) ->  AppData -> Local -> Android -> sdk -> platform-tools

<ul>
	<li>Copy this folder’s path</li>
	<li>Now right click on (My Computer/This PC), select properties</li>
	<li>A window will be opened with your PC’s basic info</li>
	<li>From the left panel of this window select ‘Advanced system settings’</li>
	<li>Another dialog will be opened -> select ‘Advanced’ tab -> Click ‘Environment Varibales…’(at the bottom of the dialog)</li>
	<li>Another dialog will be opened. From the upper part double click on ‘Path’</li>
	<li>In windows version <10 place a ‘;’ and paste the path here</li>
	<li>In windows version 10 click on ‘New’ and paste the path.</li>
	<li>Now click on all three ‘ok’ buttons and we are done</li>
</ul>
