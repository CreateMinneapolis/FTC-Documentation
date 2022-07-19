# 💻 Setup Instructions for Robot Controller and PC

## Requirements:

* 64 bit computer running Windows 7 or newer
* USB to USB Type-C cable
* Controller Hub battery

## Hardware Setup Process

### PC Software Setup

* In your browser, go to [https://www.revrobotics.com/software/](https://www.revrobotics.com/software/)
* Click on the `REV Hardware Client` link
* Install the latest version of the `REV Hardware Client`

![](<.gitbook/assets/Screenshot 2022-07-15 134143 (2) (1).png>)

* Run the installer that is downloaded

![](<.gitbook/assets/Screenshot 2022-07-15 135021 (1) (1).png>)

* Open the program

![](<.gitbook/assets/Screenshot 2022-07-15 151104 (2) (2).png>)

### Robot Controller Setup

| Steps                                                                                                                                                                              |                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Power on the Control Hub, by plugging the 12V Slim Battery ([REV-31-1302](https://www.revrobotics.com/rev-31-1302/)) into the XT30 connector labeled “BATTERY” on the Control Hub. | ![C:\Users\Rachel\AppData\Local\Microsoft\Windows\INetCache\Content.Word\g20714.png](.gitbook/assets/assets\_ftc-control-system\_-m8mwlchiogumbehgdmq\_-m8n18ghm0emnjzrchez\_48.png)     |
| The Control Hub is ready to connect with a PC when the LED turns green. Note: the light blinks blue every \~5 seconds to indicate that the Control Hub is healthy.                 | ![C:\Users\Rachel\AppData\Local\Microsoft\Windows\INetCache\Content.Word\rect22073.png](.gitbook/assets/assets\_ftc-control-system\_-m8mwlchiogumbehgdmq\_-m8n18gicw6\_gms8bess\_49.png) |
| Plug the Control Hub into the PC using a USB-A to USB-C Cable ([REV-11-1232](https://www.revrobotics.com/rev-11-1232/))                                                            |                                                                                                                                                                                          |

* Startup the REV Hardware Client. Once the Hub is fully connected it will show up on the front page of the UI under the Hardware Tab. Select the Control Hub.

![Each device that is connected will be listed.](<.gitbook/assets/Screenshot 2022-07-15 153221 (2) (2).png>)

* Click on the device. You should get to a page that looks like this:
  * You can update each of the systems of the control hub here. If there is an update, an update button will appear where the `Download` button is.

![The 'Update' page.](<.gitbook/assets/Screenshot 2022-07-15 153554 (1).png>)

* Click on `Program and Manage`
  * Here you will find your network information. The text highlighted in green is you network SSID (what you will click on when you try to connect over WiFi). The portion highlighted in yellow is your password for the network.

![The 'Program and Manage' page.](<.gitbook/assets/Screenshot 2022-07-15 160944 (2).png>)

### Wireless Communication Setup

* Now, anyone that wants to wirelessly connect to the Control Hub can just lookup the WiFi network with the name (highlighted in green), and enter in the password (in yellow).
  * From there, you can go to `192.168.43.1:8080` in your browser to get to the same page as above.
  * NOTE: CONNECTING TO THE ROBOT CONTOLLER OVER WIFI WILL DISCONNECT YOU FROM INTERNET
