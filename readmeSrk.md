## Version

### 2.1.2.3_SRK_5 --- Done
1. Update the Merlin Version

Change Log
1. Migrated to 2.1.2.3
1. Updated PID Values 
1. Enabled PID FAN Auto 
1. THERMAL_PROTECTION_PERIOD 45 
1. #define ADAPTIVE_FAN_SLOWING
1. #define WATCH_TEMP_PERIOD  45
1. Name of the Config  Senthil 5, 2.1.2.3_SRK_5

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

--- --- ---

## Firmware Update Command to be executed in the Pi


### Prcedure
```
avrdude -v -p m2560 -c wiring -P /dev/ttyACM0 -b 115200 -D -U flash:w:/home/pi/01_Firmware_30MAY24/firmware.hex
avrdude -v -p m2560 -c wiring -P /dev/ttyACM0 -b 115200 -D -U flash:w:/tmp/Marlin.ino.hex
```
--- --- ---
## Marlin Version
```
Current Version
Firmware Name: Marlin 2.1.2.3 (May 30 2024 22:48:38)  - X Axis Fix , End Stop Fix
Firmware Name: Marlin 2.1.2.3 (May 30 2024 22:32:03) - Y Direction Inverted
Firmware Name: Marlin 2.1.2.3 (May 30 2024 21:06:40)
Firmware Name: Marlin 2.0.7.2_SRK_4 (May 30 2024 19:56:47)
```

### Before 30MAY24
```
//#define SHORT_BUILD_VERSION "2.0.7.2"
//#define STRING_DISTRIBUTION_DATE "2020-07-09"
```  

## Octoprint 

### How to update Octoprint ?

1. Disable Firewall
1. Check for update in the UI
1. Install the update
1. Enable Firewall

#### Command to Disable Firewall

```
sudo ufw disable
sudo ufw enable
```

--- --- ---

#### OctoPrint Version From 30MAY24
```
OctoPrint: 1.10.1
```
#### Version Before 30MAY24
```
Version 1.8.1
```
--- --- ---

### new plugins added
```
Install OctoPod Plugin: 
Install Print History Plugin: ????
```
