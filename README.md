# Elecrow-Terminal-7-LVGL
LVGL examples for the Elecrow Terminal RGB

## Elecrow Terminal 7 LVGL Demo build instructions

A lovely ESP32 S3 board.   
https://www.elecrow.com/esp-terminal-with-esp32-3-5-inch-parallel-480x320-tft-capacitive-touch-display-rgb-by-chip-ili9488.html

<p align="center">
  <img src="https://github.com/paulhamsh/Electrow-Terminal-7-LVGL/blob/main/Elecrow-Terminal-7.png" width="400" title="Elecrow Terminal">
</p>   

## Build LVGL demos with v8.4.0    

Board manager: ESP32 S3 Dev Module   
esp32 version 2.0.16   
Arduino IDE:   2.3.2   

Install Arduino libraries:
```
  lvgl           version 8.4.0
  LoyvyanGFX     version 1.1.16
```
Get the Soruce Code.zip file from here: https://www.elecrow.com/download/product/DLC35010R/Source_Code.zip   

Make a folder and copy over ```"ESP Terminal 3.5inch RGB code\LVGL_RGB_"``` into it   
Rename the ```LVGL_RGB_``` folder and the ```LVGL_RGB_.ino``` files to something more meaningful   

Copy the lv_conf.h from ```Source Code\Libraries\lvgl.h``` to ```Arduino\libraries\lvgl\src```   
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

