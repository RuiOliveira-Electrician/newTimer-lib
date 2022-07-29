# timer-lib
![License](https://img.shields.io/github/license/rui-oliveira-tech/timer-lib)
[![GitHub release](https://img.shields.io/github/release/rui-oliveira-tech/timer-lib.svg)](https://github.com/rui-oliveira-tech/timer-lib/releases)

Timer Library. Supports Arduino AVR, SAM, STM32, ESP8266, ESP32 and SAMD21 microcontrollers.

## Installing

Download the latest version from the [release](https://github.com/rui-oliveira-tech/timer-lib/releases) section. Or even better use the builtin Library Manager in the Arduino IDE and search for "timer-lib".

The downloaded code can be included as a new library into the IDE selecting the menu:

```
 Sketch / include Library / Add .Zip library
```

The library is also available on [PlatformIO](https://platformio.org/lib/show/rui-oliveira-tech/timer-lib). You can install it by running: `pio lib install "rui-oliveira-tech/timer-lib"`. 

## Getting Started

#### Include Timer in your project:

```ino
#include <Timer.h>
```

#### Creat a new Timer:

```ino
Timer timerName(delay, scale, initialState);
```
- On delay:
```ino
1 / 5 / 10 / ...
```

- On scale:
```ino
Timer::Scale::millis / Timer::Scale::second / Timer::Scale::minute / Timer::Scale::hour
```
- On initialState:
```ino
true / false
```

## Important Functions:

```ino
Timer.getIntervalInMillis();

Timer.getTimePassedInMillis();

Timer.getTimePassedByScale();

Timer.hasEndedDelay();

Timer.reset();

Timer.force();

Timer.debug();
```
#### Example:

```ino
#include <Timer.h>

Timer newTimer(10, Timer::Scale::second, false);

void setup()
{
}

void loop()
{
  if (newTimer.hasEndedDelay())
  {
    newTimer.reset();
  }
}
```

## Others Functions:

```ino
Timer.getIntervalInMillis();

Timer.getTimePassedInMillis();

Timer.getTimePassedByScale();
```

## License

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.