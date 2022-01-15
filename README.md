# __FRC-Gorgon-Guide__
 Repository that contains all of the required materials and documentation to run gorgon-based system.

<br />


# __Overview__

## __There will be two primary sections to this tutorial:__

* Setting up the drivers station
* Setting up the Arduino to work with the Gorgon.

### __There will also be two example files and instructions on how to use them.__

<br />

# __Setting up the Gorgon Driver Station__

## ___Usage___

> 
>
>

## ___Install___

>

### __Method 1 : Zip Folder Download__

> Download the project as a zip file
>
> Extract the zip
>
> Remove the `Driver Station HTML5` folder from the unzipped folder
>
> In Chrome, version 23 or higher, visit `chrome://extensions`
>
> Switch on the developer mode toggle
>
> Select `Load Unpacked`
>
> In the pop-up box, naviagate to the extracted `Driver Station HTML5` subfolder, and continue through subfolders until the manifest.json is visible
>
>&emsp;<b>NOTE:</b> &ensp;The manifest.json might not be visible to the user; in this case, simply locate the location where manifest.json <b>should</b> be and continue with that location.
>
> The Chrome app is now loaded, to run either visit `chrome://apps` or search for `RobotOpen DS 708` in the task bar of your computer (it is now an application and can be run by one).

### __Method 2 : CRX File Download__

> Download the .crx file listed under the desired release
>
> Use an external tool to convert the .crx to a zip file
>
> In Chrome, version 23 or higher, visit `chrome://extensions`
>
> Switch on the developer mode toggle
>
> Select `Load Unpacked`
>
> In the pop-up box, naviagate to the extracted folder, continue through subfolders until the manifest.json is visible
>
> The Chrome app is now loaded, to run either visit `chrome://apps` or search for `RobotOpen DS 708`

## ___Updating___

> In Chrome, version 23 or higher, visit `chrome://extensions`
>
> Switch on the developer mode toggle
>
> Select `Update`
>
> The Chrome app is now update to the your newest download

<br />

# __Setting up the Arduino__

The first step in setting up the environment is to install the Arduino IDE:
* [Link to install](ttps://www.arduino.cc/en/software)

Once the Arduino IDE has been installed, there are a few steps to get it set up.
## __Installing the Libraries__
> Install Robot Gorgon Ethernet Library zip file. 
>
> &emsp; Link to install: https://www.arduino.cc/en/guide/libraries#toc5
>
> Once this has been installed, open the Arduino IDE
>
> Navigate to `Sketch` in the navigation bar
>
> From `Sketch` go down to `Include Library` and click `Add Zip Library`
>
> Locate the location of `RobotOpenGorgonEthernet.zip` (should still be zipped) and click `open`.
>
> You should get a notification from the Arduino IDE that the library has been installed successfully!
>
> &emsp; The library documentation is found at: https://robotopen.readthedocs.io/en/latest/
## __Setting up the IP Address of the Gorgon__
> There will be a few lines of code you will have to write in a new file for the IP Configuration of the Gorgon.
>
> First of all, write a new global variable: `IPAddress ip(*insert next step here*);`.
>
> The IPAddress constructor takes in four integers, which are the four parts of an IP Address separated by commas.
>
> For example, if you want the Gorgon's IP to be 172.0.0.1, you would write the following code: `IPAddress ip(172,0,0,1);`
>
> This IP is very important, so make sure you know it and it does not interfere with any other addresses.
>
> Next, you have to add the following line of code to the `setup()` method: `RobotOpen.setIP(ip);`
>
>These two lines of code establish a global IPAddress variable and set it as the Gorgon's IP Address
## __Setting up for and pushing code__
>&emsp;<b>NOTE:</b> &ensp;This strategy will vary for how you plan on working with the Arduino, so this documentation might not work for you!
>
> In the navigation bar, select `tools`
>
> Set the board to Arduino Ethernet from within this menu
>
> Plug into the Gorgon with a USB-A to FTDI cable
>
> After the FTDI cable is plugged in, make sure the COM port is selected (should come up with `COM3`).
>
> If there is an error with the COM3 and permissions when pushing the code, restart the computer. This solved this problem in our testing.
>
> If the robot is enabled and connected, but all of the LED's seem to state that the robot is off, <b>make sure that a controller is connected</b>. This may be the root of your problems.

<br />

# __Setting up the Driver Station__

## __Configuring the networking information__
> On the black sidebar, navigate to Setup
>
> In the setup menu, select Robot at the top
>
> Under robot connection, make sure to set `IP Address` to the one set in the code (Gorgon IP Address).
>
> The port shouldn't matter, but 22211 has been tested to be safe.
## __Running your program__
> Make sure that wireless internet is enabled. Without this, it is not possible to connect to the radio.
>
> Make sure that the radio is plugged in and ready to go. To know if this is the case, the radio should show up under network selection.
>
> Connect to the radio. When this has been done, press the Connect button on the drivers station.
>
> If a connection could be secured, press enable to enable the robot.

<br />

That should be everything needed to set up the Arduino and Gorgon for running! Thanks for reading!
