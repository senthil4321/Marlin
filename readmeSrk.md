## Version

### 2.0.7.2_SRK_3
1. Increase bed size to 200 200
1.

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

