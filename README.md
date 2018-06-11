# KeyValueEEPROM
You can use the EEPROM like a Key-Value store. 
It works with the ESP8266, ESP32 and Arduino boards.

## Installing
Install it into the Arduino libraries folder.
This library depends on [ArduinoJson](https://github.com/bblanchon/ArduinoJson).

## Getting Started.
```
KeyValueEEPROM.begin();
KeyValueEEPROM.clear();
KeyValueEEPROM.get<DataType>(String name);
KeyValueEEPROM.set<DataType>(String name, DataType value);
KeyValueEEPROM.save();
```
