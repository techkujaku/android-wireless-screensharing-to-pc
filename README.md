<h1>Tutorial on how to wirelessly share and control android screen on Windows PC using scrcpy</h1>

* Download [Windows version](https://github.com/Genymobile/scrcpy/releases/download/v1.18/scrcpy-win64-v1.18.zip) from [scrcpy github](https://github.com/Genymobile/scrcpy)
* Extract the folder to your pc
* Open command prompt and CD in the directory of the extactd folder
* Connect android devices to pc via UBS
* A pop up will appear on android phone. select transfer files
* Turn on developer options on android 
* Scroll down and turn on USB debugging mode
* Allow USB debugging. Click on always allow on this device to avoid clicking on this popup everytime usb is connected
* Type adb devices in command prompt to see if List of devices attached shows connected device
* Type adb tcpip 5555 to enable wireless mode
* type adb shell ip route
192.168.1.0/24 dev wlan0 proto kernel scope link src 192.168.1.177
