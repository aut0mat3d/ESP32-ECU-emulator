# ESP32-ECU-emulator

OBD2 ECU emulator based on CAN and OBD2 library by sandeepmisry
   https://github.com/sandeepmistry/arduino-CAN
   https://github.com/sandeepmistry/arduino-OBD2

   
This program is used to test OBD2 monitoring ESP32 board with a program 
before I connect ESP32(OBD2_02_DataPrinter.ino) ---TJA1050---CAN bus system to
my car.

   https://github.com/sandeepmistry/arduino-OBD2/blob/master/examples/OBD2_03_DataPrinter/OBD2_03_DataPrinter.ino

ESP32(ECU emulator)---TJA1050-----CAN bus connector----TJA1050 ---ESP32(OBD2_02_DataPrinter.ino)
  

# hardware

 TJA1050 CAN tranceiver board is connected to ESP32 devkitC board via
```   
  
   Vcc <- 5V  ESP32
   GND <- GND ESP32
   CTX <--- GPIO_5 ESP32 devkitC board
   CRX ---> 5V/3.3V level converter ---> GPIO_4
```
   I have used 1N5819 shotkey diode and 1kOhm pulled up to 3.3V
   to connect CRT to ESP32. 
   
   CTX is directly connected to ESP32 GPIO_5
```   
   +3.3V ----1kOhm----+
                      |
       ESP32 GPIO4 <--+----anode IN1589 cathode>|---<-CRX
```
