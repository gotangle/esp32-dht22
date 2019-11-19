# ESP32-DHT22
Esp-idf driver for DHT22 temperature and humidity sensor

## Requirements  

* [ESP32-DevKitC V4](https://docs.espressif.com/projects/esp-idf/en/v3.2.2/get-started/get-started-devkitc.html#esp32-devkitc-v4-getting-started-guide)
* xtensa-esp32 toolchain
* ESP-IDF v3.2.2

## ESP32 build system setup  

Please follow documentations to setup your toolchain and development framework.

Linux:  
* [xtensa-esp32 toolchain](https://docs.espressif.com/projects/esp-idf/en/v3.2.2/get-started-cmake/linux-setup.html) 
* [ESP-IDF](https://docs.espressif.com/projects/esp-idf/en/v3.2.2/get-started-cmake/index.html#get-esp-idf) 

Windows:
* [xtensa-esp32 toolchain](https://docs.espressif.com/projects/esp-idf/en/v3.2.2/get-started-cmake/windows-setup.html#standard-setup-of-toolchain-for-windows-cmake) 
* [ESP-IDF](https://docs.espressif.com/projects/esp-idf/en/v3.2.2/get-started-cmake/index.html#windows-command-prompt) 

**Notice: We use the ESP-IDF v3.2.2, make sure you clone the right branch of ESP-IDF**

```
git clone -b v3.2.2 --recursive https://github.com/espressif/esp-idf.git
```

Now, you can test your develop environment via the [hello_world](https://github.com/espressif/esp-idf/tree/release/v3.2/examples/get-started/hello_world) project.  

```shell
cd ~/esp
cp -r $IDF_PATH/examples/get-started/hello_world .
idf.py menuconfig
idf.py build
idf.py -p /dev/ttyUSB0 flash && idf.py -p /dev/ttyUSB0 monitor
```

The output would be something like:  

```shell
I (0) cpu_start: App cpu up.
I (184) heap_init: Initializing. RAM available for dynamic allo
cation:
I (191) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (197) heap_init: At 3FFB2EF8 len 0002D108 (180 KiB): DRAM
I (204) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (210) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (216) heap_init: At 40089560 len 00016AA0 (90 KiB): IRAM
I (223) cpu_start: Pro cpu start user code
I (241) cpu_start: Starting scheduler on PRO CPU.
I (0) cpu_start: Starting scheduler on APP CPU.
Hello world!
This is ESP32 chip with 2 CPU cores, WiFi/BT/BLE, silicon revision 1, 4MB external flash
Restarting in 10 seconds...
Restarting in 9 seconds...
```

You can press `Ctrl` + `]` to exit the monitor and ready for the next setup.    

## Building and flashing to ESP32

### Step 1: cloning repository  

```shell
git clone https://github.com/gotangle/esp32-dht22.git
cd esp32-dht22
```

### Step 2: Build & Run

```shell
idf.py build
idf.py -p /dev/ttyUSB0 flash && idf.py -p /dev/ttyUSB0 monitor
```

Output: 
![](https://github.com/gotangle/esp32-dht22/blob/master/images/result.PNG)