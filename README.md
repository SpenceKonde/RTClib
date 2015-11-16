This is a fork of Adafruit's fork of JeeLab's fantastic real time clock library for Arduino, adding support for AVR boards that don't support hardware I2C, or do so only through the USI. 

At present no testing of any sort has been conducted, this is expected to change within days. 

# Installation #

To download. click the DOWNLOADS button to the right, and rename the uncompressed folder RTClib_Tiny.

Place the RTClib folder in your *arduinosketchfolder*/libraries/ folder. 
You may need to create the libraries subfolder if its your first library. Restart the IDE.

# Compatibility #

This library is designed ONLY for use with AVR-based boards on Arduino 1.0.x or later. For SAM/Due/ESP8266, use Adafruit's version. While the purpose is support for ATTiny chips, the library should work with ATmega chips that have proper hardware I2C as well.


Board              | Wire Library | Notes
------------------ | :----------: | ----------
ATmega328          |   Wire.h       |              
ATtiny1634          |   TinyWireM.h       |          
ATtiny841          |   SoftI2CMaster.h       |          
ATtiny828          |   SoftI2CMaster.h       |   
ATtiny85           | TinyWireM.h     |           
ATtiny84        |   TinyWireM.h       |           
ATtiny88          |   Wire.h       |           
ATtiny167          |   TinyWireM.h       |            
ATtiny4313          |   TinyWireM.h       |           
ATtiny861          |   TinyWireM.h       |             

For TinyWireM, use the version from https://github.com/SpenceKonde/TinyWireM
For SoftI2CMaster, use the version from https://github.com/todbot/SoftI2CMaster or https://github.com/SpenceKonde/SoftI2CMaster

# Using # 

Your sketch should #include the appropriate wire library per table above. 

If using SoftI2CMaster, you must declare in your sketch:

```

SoftI2CMaster softi2c=SoftI2CMaster(sclPin,sdaPin,0); //where sclPin and sdaPin are the pins used for SCL and SDA respectively. 

```

Aside from that consideration, this may be used like the normal RTClib. See the examples for more.
