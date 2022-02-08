# How to flash ESP32 wirelessly?
*Tested with both android and laptop*
1. Upload the raw [skeleton code](https://github.com/TUdayKiranReddy/Intro-to-UAV/blob/main/wireless_flashing/skeleton.cpp) to ESP32 with a micro USB cable (*Add your network credentials in file*).
2. Find out the IP of ESP32.
3. If you are utlising BLUETOOTH of ESP32 in your project then got to Step 4. Else use the skeleton code itself to upload the firmware  **NOTE:- Do not alter functions OTAsetup() or OTAloop(), if modified we will not be able to reupload the code once again wirelessly and have to follow the procedure from Step 1.**
4. Append the following line in platform.ini of your project
```
upload_protocol = espota
```
5. Now upload the bin file OTA(Over The Air) (*Ensure that both deivce and ESP32 are on same network*).
```
pio run -t upload --upload-port $ESP32_IP
```
