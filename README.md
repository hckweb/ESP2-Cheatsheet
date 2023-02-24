# ESP32 Cheatsheet
## Writing Flash
### Single Writing Flash
```cmd
.\esptool.exe --port COM23 write_flash 0x00000 flash_ok_empty.bin
```
### Multiple Writing Flash
```cmd
.\esptool.exe --port COM23 write_flash 0x10000 firmware.bin 0x910000 spiffs.bin
```
- - - -
## Reading Flash
```cmd
.\esptool.exe -p COM23 -b 460800 read_flash 0 0x1000000 flash_ok_empty.bin
```
- - - -
## Core Dump
Read coredump partition. Offset: `1114112` Size: `65536`
```cmd
esptool.py --port /dev/ttyUSB0 read_flash 1114112 65536 core.bin
```
Print Core Dump
```cmd
espcoredump.py info_corefile -t raw -c core.bin build/download-file.elf
```
