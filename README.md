# Elecrow-Terminal-7-LVGL
LVGL examples for the Elecrow Terminal RGB

## Elecrow Terminal 7 LVGL Demo build instructions

A lovely ESP32 S3 board.   
https://www.elecrow.com/esp-terminal-with-esp32-3-5-inch-parallel-480x320-tft-capacitive-touch-display-rgb-by-chip-ili9488.html

<p align="center">
  <img src="https://github.com/paulhamsh/Electrow-Terminal-7-LVGL/blob/main/Elecrow-Terminal-7.png" width="400" title="Elecrow Terminal">
</p>   

The wiki is here: https://www.elecrow.com/wiki/esp32-display-702727-intelligent-touch-screen-wi-fi26ble-800480-hmi-display.html  


## Build LVGL demos with v8.4.0    

Board manager: ESP32 S3 Dev Module   
esp32 version 2.0.16   
Arduino IDE:   2.3.2   

Install Arduino libraries:
```
  lvgl           version 8.4.0
  LoyvyanGFX     version 1.1.16
  TAMC-GT911     version 1.0.2
```
Get the Arduino_7inch.zip file from here: https://www.elecrow.com/download/product/DLC35010R/Source_Code.zip     

Make a folder and copy over ```HMI-7``` into it  (for board type  WZ8048C070 - if a different board type read the README.txt)   

Copy the lv_conf.h from ```Arduino_7inch\Libraries\lv_conf.h``` to ```Arduino\libraries\lvgl\src\lv_conf.h```   





Edit this line:  
```
  #define LV_FONT_MONTSERRAT_24 1   
```
Copy folders ```Arduino\libraries\lvgl\demos``` and ```Arduino\libraries\lvgl\examples```  to ```lvgl\src```   

Also: hold down the Boot button and press the RESET button to initiate firmware download mode   

There is a pre-build lv_conf.h in the v8 folder.   

## Build LVGL demos with v9.1.0

Board manager: ESP32 S3 Dev Module   
esp32 version 2.0.16   
Arduino IDE:   2.3.2   

Install Arduino libraries:
```
  lvgl           version 9.1.0
  LoyvyanGFX     version 1.1.16
```

Copy ```Arduino\libraries\lvgl\lv_conf_template.h``` to ```src\lv_conf.h```   
Copy folders ```Arduino\libraries\lvgl\demos``` and ```Arduino\libraries\lvgl\examples```  to ```Arduino\libraries\lvgl\src```     
Edit
```
#if 1 /*Set it to "1" to enable content*/
#define LV_USE_DEMO_WIDGETS 1
#define LV_FONT_MONTSERRAT_24 1
```
Use the LGVL_V9_RGB.ino in the v9 folder       
There is a pre-build lv_conf.h in the v9 folder.   

