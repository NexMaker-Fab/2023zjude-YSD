# <font color="#99CCFF">Case Study</font>

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


// microSD卡
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
Arduino_ST7701_RGBPanel *gfx = 新的Arduino_ST7701_RGBPanel（
总线，GFX_NOT_DEFINED /* RST */，0 /*旋转*/，
true /* IPS */, 480 /* 宽度 */, 480 /* 高度 */,
st7701_type1_init_operations，sizeof（st7701_type1_init_operations），
true /* BGR */);
```

- Set music playback and image display loop tasks.

```C++
void Task_TFT(void *pvParameters) // 这是一个任务。
{
 while (1) // 任务永远不会返回或退出。
 {
 Serial.println(image_list[image_index % IMAGE_COUNT]);
 jpegDraw(image_list[image_index++ % IMAGE_COUNT].c_str()), jpegDrawCallback, true, 0, 0, gfx->width(), gfx->height());

  vTaskDelay（2000）；
  }
 }

  void Task_Audio(void *pvParameters) // 这是一个任务。
 {
  而（1）
  audio.loop（）；
 }

 void audio_eof_mp3（const char *info）
 { // 文件结束
 Serial.print("eof_mp3 ");
 Serial.println（信息）；

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


## 2 Audio Memory Chest

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.1.png" width = "800"/>
</div>

### 2.1 Introduction 
The author places small objects, souvenirs collected around the world, and sounds captured with an mp3 recorder (market, street sounds, music, etc.) in the memory box, and every time a drawer is opened, a random audio file recorded in that location is played to evoke the memory of the time.

### 2.2 Parts List

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.3.png" width = "800"/>
</div>

**Electronics**:
Most of these can be found on Sparkfun, Amazon, or Digikey.
- Arduino Pro Mini
- YX5300 Serial MP3 player
- Adafruit audio amplifier
- MCP23017 Port expander
- US5881 Hall Effect sensors (one for each drawer)
- Stereo switching potentiometer/knob
- 3" Speakers
- 3.5mm audio plug
- Standard 2.1 x 5.5mm DC power jack
- Female and male headers
- Molex Connectors and sockets
- Screw-in PCB terminal block
- Rare earth magnets (one for each drawer)
- Blank double-sided copper PCB
- 10-wire Ribbon Cable
- Mono RCA cable
- Two RCA jacks
- 10k resistors
- 100uf electrolytic capacitor
**Other materials**:
- A chest with several drawers
- Felt (for drawer interior)
- Black pantyhose for speaker grilles
- 1/4 inch MDF or plywood for speaker enclosures
- 3/4 inch birch plywood for external case
- screw-on legs for external case

### 2.3 Production process
**Step 1**: Clean and Prepare Drawers

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.4.jpg" width = "800"/>
</div>

- Clean the whole thing. Drill holes for each sensor, cut the felt and glue it to the bottom of the drawer.
**Step 2**: Build Speaker Enclosures

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.5.jpg" width = "800"/>
</div>

**Step 3**: Create Main Board and Sensor Array Boards

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.6.jpg" width = "800"/>
</div>

**Step 4**: Load Audio Onto SD Card, Tweak Arduino Code
- Using an SD adaptor, open a microSD card to your computer.
- Make a folder for each drawer on the top level of the card. Number them sequentially starting with 1.
- Select the mp3s you want to play when each drawer opens, and drag them into the drawer's folder. The code will cycle through them randomly when the drawer is opened.
- Rename the files in each folder so they start with sequential numbers: (001_file.mp3, 002_file.mp3, etc)
- Eject the card and insert into serial mp3 player.
**Step 5**: Install Electronics

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.7.jpg" width = "800"/>
</div>

**Step 6**: Wire Together Sensors and Plug Into Main Board

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.8.png" width = "800"/>
</div>

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.9.jpg" width = "800"/>
</div>

**Step 7**: Build Wooden Box/Case

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.10.png" width = "800"/>
</div>

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/case2.2.png" width = "800"/>
</div>