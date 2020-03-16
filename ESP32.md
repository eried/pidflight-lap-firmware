# ESP32 based timer #

## Parts ##
* ESP32 TTGO T8 https://s.click.aliexpress.com/e/_d6sfNUb Reference: https://github.com/LilyGO/TTGO-T8-ESP32
* RX5808 https://s.click.aliexpress.com/e/_dUaM1rh
* 2x 4.7K resistors
* Small battery (optional) i.e.: https://aliexpi.com/ZSsn
* Buzzer (optional) https://s.click.aliexpress.com/e/_d75AAWT

## Pinout ##
| ESP32 T8 | RX5880 | Comments |
| :------------- |:-------------| :-----|
| 34 | RSSI | Via resistor divider |
| GND | GND | |
| 19 | CH1 | |
| 22 | CH2 | |
| 23 | CH3 | |
| Switch | +5V | Directly to the middle leg of the ON/OFF switch |

* The optional **Buzzer** goes to pin 15 and GND

### Switch 

VCC in the ESP32 is not powered when the board is running of the battery, so we need to tap directly to the middle pin of the switch as shown here:
![](images/vbat.PNG)

### Resistor divider

    RSSI ------ 4.7K ------ Pin 34 ------ 4.7K ------ GND

RSSI from the RX5880 may oscilate between 5V (if powered by USB) and 4.3V to 3.5V (if powered by the battery). The RX5880 +5V pin is tolerant of that range https://www.foxtechfpv.com/product/5.8G%20modules/rx5808/RX5808-Spec-V1.pdf however, the ESP32 is not so this resistor divider is just to half that voltage. 

The ESP32 uses pin 35 internally to measure that voltage reference and provide a right RSSI value.

## Case
IMAGE
