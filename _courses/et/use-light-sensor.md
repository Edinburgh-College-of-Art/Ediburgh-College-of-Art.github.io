---
layout: page
title: ! 'micro:bit Light Sensor'
course: Electronic Things
repo_url: electronic-things
order: 2
week: 1
---

## On board LEDs

In [MakeCode](https://makecode.microbit.org) you can use the onboard LEDs to get a rough sense of light intensity.

Try creating this snippet

<pre id="pre1" class="makecode">
basic.forever(() => {
    basic.showNumber(input.lightLevel() / 28)
})
</pre>

## Light Dependant Resistor

You can also use a light dependant resistor in much the same way as you would with an Arduino

![LDR micro:bit wiring](https://cdn-learn.adafruit.com/assets/assets/000/051/035/original/temperature___humidity_breadboard_light.png?1518686853)


### Code

#### Blocks

<pre id="pre1" class="makecode">
let number = 0
let reading = 0
basic.forever(() => {
    reading = pins.analogReadPin(AnalogPin.P2)
    number = reading / 50
    basic.showNumber(number)
})
</pre>


#### Arduino

```cpp
#include <Adafruit_Microbit.h>

Adafruit_Microbit_Matrix microbitMatrix;
int lightSensorPin = 2;

void setup()
{
  microbitMatrix.begin();
}

void loop()
{
  int sensorValue = analogRead(sensorPin);
  microbitMatrix.print(sensorValue);  // pi time, 4 digits of precision!!
}
```
