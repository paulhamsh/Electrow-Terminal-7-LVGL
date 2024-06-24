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

Comment out the parts of the code using the UI library    
```
//UI
//#include <ui.h>
```

```
/*
  ui_init();//Boot UI
  while (1)
  {
    
    if (goto_widget_flag == 1)//Go to widget
    {
      if (ticker1.active() == true)
      {
        ticker1.detach();
      }
      goto_widget_flag = 0;
      delay(300);
     break;
    }

    if (goto_widget_flag == 3)//Go to the touch screen and close the progress bar thread first
    {
      bar_flag = 0; //Stop progress bar sign
      if (ticker1.active() == true)
      {
        ticker1.detach();
      }
      if (first_flag == 0 || first_flag == 1)
      {
        label_xy();
        first_flag = 2;
      }
      if (zero_clean == 1)
      {
        touch_last_x = 0;
        touch_last_y = 0;
        zero_clean = 0;
     }
      lv_label_set_text(ui_Label, "Touch Adjust:");
      lv_label_set_text_fmt(ui_Label3, "%d  %d", touch_last_x, touch_last_y); //Display touch information
    }

    if (goto_widget_flag == 4)
    {

      val = 100;
      delay(100);
      ticker1.attach_ms(20, callback1);
      goto_widget_flag = 0;
    }

    if (goto_widget_flag == 5) //Trigger Calibration Signal
    {

      lv_scr_load_anim(ui_touch_calibrate, LV_SCR_LOAD_ANIM_NONE, 0, 0, false);
      lv_timer_handler();
      lv_timer_handler();
      delay(100);
     touch_calibrate();//Touch Calibration
      lv_scr_load_anim(ui_TOUCH, LV_SCR_LOAD_ANIM_NONE, 0, 0, false);
      lv_timer_handler();
      goto_widget_flag = 3; //Access to the touch screen logo
      touch_last_x = 0;
      touch_last_y = 0;
    }

    if (bar_flag == 6)//Runs the progress bar once when you first boot into the Menu screen, then stops running after that
    {
      if (first_flag == 0)
      {
       lv_example_bar();
        ticker1.attach_ms(20, callback1);
        first_flag = 1;
      }
    }

    lv_timer_handler();
  }

*/
```
Comment out these functions  ```void lv_example_bar(void)```  and ```void callback1()``` and ```void touch_calibrate()```     
Comment out the two lines containing ```lcd.fillScreen(BLACK);```   
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

