# Setting_up_new_FC
Steps to be followed for setting fresh board(without boot loader/firmware) Windows specific:-

* First Install Dfuse demo from stm ( https://www.st.com/en/development-tools/stsw-stm32080.html )

* Open dfu manager which get installed with above package.

  ![](https://github.com/bhaskarsdose/Setting_up_new_FC/blob/master/dfu_1.PNG)

* select GENERATE HEX file button and click next(ONLY USE HEX, BIN DON'T WORK).

* In next window select s19 and HEX button.

  ![](https://github.com/bhaskarsdose/Setting_up_new_FC/blob/master/dfu_2.PNG)

* Select the .hex file generated using the command

  ```
  ./waf configure --board BOARDNAME --bootloader
  ./waf bootloader
  ```

  or download prebuilt hex file from:-

   https://firmware.ardupilot.org/Tools/Bootloaders/ 

* Click on generate button for getting .dfu file on preferred location.

* After getting .dfu file open DfuseDemo,

  ![](https://github.com/bhaskarsdose/Setting_up_new_FC/blob/master/se_1.PNG)

* In Dfusedemo choose the .dfu file and connect your board in dfu mode and click on upgrade and only do this in upgrade and verify section only.

  ![](https://github.com/bhaskarsdose/Setting_up_new_FC/blob/master/se_2.PNG)

Done, Reconnect your board and check its led and see in device manager for ensuring that bootloader is burned successfully if your board is detected then move to burn ardupilot firmware using MISSION PLANNER by following these steps:-

* Open mission planner and go to INITIAL SETUP<Install Firmware.

  ![](https://github.com/bhaskarsdose/Setting_up_new_FC/blob/master/fc_1.PNG)

* Then click on "Load custom firmware"

  ![](https://github.com/bhaskarsdose/Setting_up_new_FC/blob/master/fc_2.PNG)

* Select the correct .apj file generated using command:

  ```
  ./waf configure --board BOARDNAME
  ./waf copter
  ```

  or download from,

   https://firmware.ardupilot.org/Copter/ 

After selecting the file wait for the installation it will take around 1min. after that read the instruction appear on mission planner and its done!!!

If everything followed correctly then you can able to connect your new board with your custom firmware or latest build.

Created by:

Bhaskar Dutt