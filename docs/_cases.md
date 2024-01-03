# <font color="#99CCFF">Similar Cases</font>

## 1 DIY E-Album

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case1.1.png" width = "800"/>
</div>

### 1.1 Introduction 
When the author lived in the country as a child, it was a very memorable time for him. The author hopes to save the good memories as pictures and display them in the form of electronic albums, and play music through speakers while the photos are displayed, so that the memories of the time can be reproduced.

### 1.2 Materials used

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case1.2.png" width = "800"/>
</div>

- ESP32-S3 Parallel TFT with Touch 4.0, with 480*480 resolution, it integrated display/ touch/ audio speaker/ Lipo charger, to make this product ideal for electronic photo frame. It would be a nice experience to be able to show pictures and play music at the same time!
- 3D printer: It needs to be used to print the required brackets.
- screw, nut and isolation column.

### 1.3 Production process
**Step 1**: Hardware Assembly and Bracket by 3D-Printing

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case1.3.png" width = "800"/>
</div>

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case1.4.png" width = "800"/>
</div>

**Step 2**: Software
Development environment is Arduino IDE.Get the code in GitHub. Can be designed as a reference program.

- Declaration uses file and pin definitions to enable the program to successfully drive the chip to read images and music resources from the SD card.
```C++
#include "Audio.h"
#include "Arduino_GFX_Library.h"
#include "JpegFunc.h"


// microSD card
#define SD_SCK 12
#define SD_MISO 13
#define SD_MOSI 11
#define SD_CS 10


// I2S
#define I2S_DOUT 19
#define I2S_BCLK 20
#define I2S_LRCK 46


// TFT
#define TFT_BL -1


#define AUDIO_FILENAME_01 "/ChildhoodMemory.mp3"
```

- Initialize screen parameters, The screen uses the ST7701 driver.
```C++
Arduino_ST7701_RGBPanel *gfx = new Arduino_ST7701_RGBPanel(
    bus, GFX_NOT_DEFINED /* RST */, 0 /* rotation */,
    true /* IPS */, 480 /* width */, 480 /* height */,
    st7701_type1_init_operations, sizeof(st7701_type1_init_operations),
    true /* BGR */);
```

- Set music playback and image display loop tasks.
```C++
void Task_TFT(void *pvParameters) // This is a task.
{
    while (1) // A Task shall never return or exit.
    {
        Serial.println(image_list[image_index % IMAGE_COUNT]);
        jpegDraw(image_list[image_index++ % IMAGE_COUNT].c_str(), jpegDrawCallback, true, 0, 0, gfx->width(), gfx->height());


        vTaskDelay(2000);
    }
}


void Task_Audio(void *pvParameters) // This is a task.
{
    while (1)
        audio.loop();
}


void audio_eof_mp3(const char *info)
{ // end of file
    Serial.print("eof_mp3     ");
    Serial.println(info);


    audio.connecttoFS(SD, AUDIO_FILENAME_01); //"/ChildhoodMemory.mp3"
}
```

**Step 3**: Test and Result

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case1.5.png" width = "800"/>
</div>

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case1.6.png" width = "800"/>
</div>

- Connect the screen and bracket with screw, nut and isolation column.
- Using the card reader, move image files and audio files from the computer to the SD card.
- Verify and upload the code.
- Use a USB cable or plug in a battery. (Or USB supply power)
