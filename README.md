# 触摸板
用于使用ESP32、触摸屏和BLE与Windows/macOS/Linux接口。
# # #(用户指南)(https://github.com/DustinWatts/FreeTouchDeck/wiki)

# ESP32触地得分用户

确保取消注释' //#define USECAPTOUCH ' !
如果你想使用扬声器，取消注释' //#define speakerPin 26 '

如果FreeTouchDeck是预先安装的，你可以在这里找到如何设置配置器:
https://github.com/DustinWatts/esp32-touchdown/wiki/With-FreeTouchDeck-pre-installed

删除旧的克隆，使用新的

###混合不同版本的文件可能会导致一些意想不到的行为!

重要的是要意识到，因为这是一个测试版本，更改te代码经常发生。FreeTouchDeck。Ino和其他文件(例如数据文件夹中的文件)相互依赖，它们是一体的。因此，当您下载新版本时，请确保只使用当前下载的文件，而不是来自其他版本的文件。最好的做法是完全删除旧版本，然后下载/克隆新版本，以确保您不会意外地混合来自不同版本的文件。**下载/复制最新版本后，请使用“ESP32 Sketch data upload”再次上传“data”文件夹

# Beta版本!

这个版本还处于非常早期的开发阶段。很有可能，如果你没有使用确切的
和我一样，你也会遇到问题的。但这就是这个版本的目的:找出需要什么
使FreeTouchDeck在大多数ESP和TFT屏幕上工作。此外，还缺乏逐步编写的文档。

#硬件使用

我目前使用的硬件是:

电阻式触控:
-一个ESP32 DEVKIT V1 (WROOM32)(分区方案:没有OTA与2MB的应用程序和2MB的SPIFFS)
-一个3.5寸(480x320) TFT +触摸屏，ILI9488驱动和XPT2046电阻触摸控制器

电容式触摸:
-一个ESP32 DEVKIT V1 (WROOM32)(分区方案:没有OTA与2MB的应用程序和2MB的SPIFFS)
- 3.5寸(480x320) TFT +触摸屏，ILI9488驱动和FT6236电容触摸控制器

# !-库依赖-!
- Adafruit-GFX-Library(版本1.10.0或更高)，可通过库管理器
- TFT_eSPI(版本2.2.14或更高)，可通过库管理器获得
—esp32 - bly - keyboard (forked)(最新版本):https://github.com/DustinWatts/ESP32-BLE-Keyboard下载
—ESPAsyncWebserver(最新版本)下载地址:https://github.com/me-no-dev/ESPAsyncWebServer
—AsyncTCP(最新版本)从https://github.com/me-no-dev/AsyncTCP下载
- ArduinoJson(版本6.16.1或更高)，可通过库管理器

如果使用电容式触摸:
—FT6236(最新版本)，下载地址:https://github.com/DustinWatts/FT6236

# Combiner PCB for an ESP32 DevKit C (38-pin only) + ILI9488 Touch Module:

https://github.com/DustinWatts/ESP32_TFT_Combiner

# TFT_eSPI配置

在编译和上传FreeTouchDeck之前。如果没有草图，你必须编辑TFT_eSPI库中包含的**user_setup.h**文件。这可以在Arduino skechtbook文件夹“libraries”下找到。如果您没有重命名TFT_eSPI库文件夹，可以在**TFT_eSPI-master**中找到文件**user_setup.h**。在这里，您必须取消对应用于硬件配置的行进行注释。例如:如果你有一个带有ILI9488驱动程序的TFT，你必须取消“Section 1”下面的注释。确保所有其他驱动程序都被注释掉了!

下一节是“第二节”。这也取决于您使用的硬件。例如，对于ESP32，你必须取消注释' EDIT the PIN NUMBERS IN the LINES IN the FOLLOWING to SUIT YOUR ESP32 '下面的#define(s)。此外，如果你的TFT有黑光控制引脚可用，你必须取消注释在' #define TFT_BL '和' #define TFT_BACKLIGHT_ON '下找到的行。

“第三部分”可以不用管。

#帮助

你可以加入我的Discord服务器，我有一个专用的# freettouchdeck频道。https://discord.gg/RE3XevS
For interfacing with Windows/macOS/Linux using an ESP32, a touchscreen and BLE.

### [User guide](https://github.com/DustinWatts/FreeTouchDeck/wiki)

# ESP32 TouchDown users

Make sure to uncomment the line `//#define USECAPTOUCH`!   
And if you wish to use the speaker uncomment the line `//#define speakerPin 26`

If FreeTouchDeck came pre-installed, you can find how to set up the configurator here:   
https://github.com/DustinWatts/esp32-touchdown/wiki/With-FreeTouchDeck-pre-installed

# Delete the old clone and use the new

### Mixing files of different versions may cause some unexpected behavior!

Important to realise is that since this is a beta version, changes to te code happen frequently. The FreeTouchDeck.ino and other files (for example in the data folder) rely on each other, they come as one. So when you download the new version, make sure that you only use the files that come with the current download, and not files from other versions. Best practise is to completely delete the old version and then download/clone the new version to make sure you do not accidently mix files from different versions. **After downloading/cloning the latest version, make sure to also upload the "data" folder again using 'ESP32 Sketch Data Upload".**

# Beta Version!

This version is in it's very early stages of development. Chances are that if you are not using the exact
same setup as I am, you will run in to problems. But that is what this version is for: finding out what is needed
to make FreeTouchDeck work across most ESP's and TFT screens. Also there is a lack of documentation which is gradually being written.

# Hardware used

The hardware I currenlty use is:

For Resistive touch:
- an ESP32 DEVKIT V1 (WROOM32) (Partition scheme: NO OTA with 2MB app and 2MB SPIFFS)
- an 3.5" (480x320) TFT + Touchscreen with ILI9488 driver and XPT2046 resitive touch controller

For Capacitive touch:
- an ESP32 DEVKIT V1 (WROOM32) (Partition scheme: NO OTA with 2MB app and 2MB SPIFFS)
- an 3.5" (480x320) TFT + Touchscreen with ILI9488 driver and FT6236 capacitive touch controller

# !- Library Dependencies -!
- Adafruit-GFX-Library (version 1.10.0 or higher), available through Library Manager
- TFT_eSPI (version 2.2.14 or higher), available through Library Manager
- ESP32-BLE-Keyboard (forked) (latest version) download from: https://github.com/DustinWatts/ESP32-BLE-Keyboard
- ESPAsyncWebserver (latest version) download from: https://github.com/me-no-dev/ESPAsyncWebServer
- AsyncTCP (latest version) download from: https://github.com/me-no-dev/AsyncTCP
- ArduinoJson (version 6.16.1 or higher), available through Library Manager

If you use capacitive touch:
- FT6236 (latest version), download from: https://github.com/DustinWatts/FT6236

# Combiner PCB for an ESP32 DevKit C (38-pin only) + ILI9488 Touch Module:

https://github.com/DustinWatts/ESP32_TFT_Combiner

# TFT_eSPI configuration

Before compiling and uploading the FreeTouchDeck.ino sketch, you will have to edit the **user_setup.h** file included with the TFT_eSPI library. This can be found in your Arduino skechtbook folder under "libraries". If you have not renamed the TFT_eSPI library folder, the file **user_setup.h** can be found in **TFT_eSPI-master**. Here you will have to uncomment the lines that apply to you hardware configuration. For example: if you have an TFT with an ILI9488 driver, you will have to uncomment that line under `Section 1`. Make sure all the other drivers are commented out!  

The next section is `Section 2`. This also depends on what hardware you are using. For example for an ESP32 you'll have to uncomment the correct #define(s) under `EDIT THE PIN NUMBERS IN THE LINES FOLLOWING TO SUIT YOUR ESP32 SETUP`. Also if your TFT has the blacklight control pin available you will have to uncomment the lines found under `#define TFT_BL` and `#define TFT_BACKLIGHT_ON`.  

"Section 3" can be left alone.   

# Help

You can join my Discord server where I have a dedicated #freetouchdeck channel. https://discord.gg/RE3XevS
