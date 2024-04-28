## Version

### 2.0.7.2_SRK_4
1. Update bed size to 205 165
```c
// @section machine
//https://reprap.org/wiki/Configuring_Marlin_Bed_Dimensions
// The size of the print bed
#define X_BED_SIZE 205 // 140
#define Y_BED_SIZE 165 // 100

// Travel limits (mm) after homing, corresponding to endstop positions.
#define X_MIN_POS -25
#define Y_MIN_POS -35
```

### 2.0.7.2_SRK_3
1. Increase bed size to 200 200

### 2.0.7.2_SRK_1
1. Add inbuild solid state relay for the heatbed
1. Increase Heatbed temperature to 70 *C
1. Set the build area to 120 X * 100 Y
1. Add version handling


## Remote push scripts
```
pscp -pw Kse1pl Marlin.ino.hex pi@pi2.local:/tmp
ssh pi@pi2.local
avrdude -v -p m2560 -c wiring -P /dev/ttyACM0 -b 115200 -D -U flash:w:/tmp/Marlin.ino.hex
```
### FAN
```
#define E0_AUTO_FAN_PIN 6
#define E1_AUTO_FAN_PIN -1
#define E2_AUTO_FAN_PIN -1
#define E3_AUTO_FAN_PIN -1
#define E4_AUTO_FAN_PIN -1
#define E5_AUTO_FAN_PIN -1
#define E6_AUTO_FAN_PIN -1
#define E7_AUTO_FAN_PIN -1
#define CHAMBER_AUTO_FAN_PIN -1

#define EXTRUDER_AUTO_FAN_TEMPERATURE 30
#define EXTRUDER_AUTO_FAN_SPEED 255   // 255 == full speed
#define CHAMBER_AUTO_FAN_TEMPERATURE 30
#define CHAMBER_AUTO_FAN_SPEED 255
```
