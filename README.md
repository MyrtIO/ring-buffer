# RingBuffer

A simple C++ ring buffer. Can be used with Arduino Framework as it implements [Stream](https://docs.arduino.cc/language-reference/en/functions/communication/stream/) interface.

## Usage

```cpp
#include <Arduino.h>
#include <RingBuffer.h>

RingBuffer<2> buffer;

void loop() {
    buffer.write(millis());
    buffer.write(millis());
    while (buffer.available() > 0) {
        Serial.println(buffer.read());
    }
}
```