<h1>Tutorial on how to wirelessly share and control android screen on Windows PC using scrcpy</h1>

* Download [Windows version](https://github.com/Genymobile/scrcpy/releases/download/v1.18/scrcpy-win64-v1.18.zip) from [scrcpy github](https://github.com/Genymobile/scrcpy)
* Extract the folder to your pc
* Open command prompt and CD in the directory of the extactd folder
* Example: the extracted folder is located in D, type the following commands:
![image](https://user-images.githubusercontent.com/87014174/125895658-9d5d4f30-9e42-49a0-a090-057cb531c03c.png)

* Connect android devices to pc via USB
* A pop up will appear on android phone. select transfer files
* Turn on [developer options](https://www.digitaltrends.com/mobile/how-to-get-developer-options-on-android/) on android 
* Scroll down and turn on USB debugging mode
* Allow USB debugging. Click on always allow on this computer to avoid clicking on this popup everytime usb is connected
* Type adb devices in command prompt to see if List of devices attached shows connected device
* Type adb tcpip 5555 to enable wireless mode
* type adb shell ip route
* Example output:
  ```
  192.168.1.0/24 dev wlan0 proto kernel scope link src 192.168.1.177<--- This is your connected device ip
   ```
* Type adb connect 192.168.1.177
* Before removing the usb check that "Allow ADB debugging in charge only mode" is enable. This is required on some devices like Huawei phones.
* 
*![image](https://user-images.githubusercontent.com/87014174/125895299-474b8349-6105-4ecf-b5df-d94be476f6d8.png)

* Remove the usb cable. Toggle USB debugging OFF and ON again
* Type adb devices
* Example output:
```
List of devices attached
192.168.1.177:5555      device
```
  This shows that device is successfully connected online. 
 * If device is constantly offline type adb kill-server and repeat from #Connect android devices to pc via USB
 
 * Type scrcpy and a window will appear on your desktop. You might need 
