# Grove Sunlight Sensor

This library is used from controlling the Grove Sunlight sensor on mbed-os.

## Example Usage

Example program showing how this library is used:

```C++
#include "mbed.h"
#include "SI114X.h"

SI114X light_sensor(D14, D15);

// main() runs in its own thread in the OS
int main()
{
    while (!light_sensor.Begin()) {
        printf("Initializing light sensor\r\n");
        wait(1);
    }
    while (true) {
        printf("Visible: %i\r\n", light_sensor.ReadVisible());
        printf("IR: %i\r\n", light_sensor.ReadIR());
        printf("UV: %i\r\n", light_sensor.ReadUV());
        wait(1);
    }
}
```
