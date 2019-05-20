# KeyValueEEPROM
You can use the EEPROM like a Key-Value store. 
It works with the ESP8266, ESP32 and Arduino boards.

## Installing
Install it into the Arduino libraries folder.
This library depends on [ArduinoJson](https://github.com/bblanchon/ArduinoJson).

## Example
```
// Set this definition, if you want to change the EEPROM size.
// #define KeyValueEEPROM_SIZE 1024

// Include KeyValueEEPROM library.
#include <KeyValueEEPROM.h>

void setup() {
  // Begin serial-connection.
  Serial.begin(115200);

  // Begin KeyValueEEPROM library.
  KeyValueEEPROM.begin();

  // Print values from EEPROM.
  if (KeyValueEEPROM.exists("Name") && KeyValueEEPROM.exists("Surname")) {
    Serial.println("Values from EEPROM:");
    Serial.println("Name = " + KeyValueEEPROM.get<String>("Name"));
    Serial.println("Surname = " + KeyValueEEPROM.get<String>("Surname"));
  } else {
    Serial.println("EEPROM is empty.");
  }

  // Write values.
  KeyValueEEPROM.set<String>("Name", "Doe");
  KeyValueEEPROM.set<String>("Surname", "John");

  // Save to EEPROM.
  KeyValueEEPROM.apply();

  // Print current written values.
  Serial.println("\nCurrent written values:");
  Serial.println("Name = " + KeyValueEEPROM.get<String>("Name"));
  Serial.println("Surname = " + KeyValueEEPROM.get<String>("Surname"));
}

void loop() {
}
```
## License
This library is licensed under the GPL3.
