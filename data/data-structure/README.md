# Structure

## Table of Contents

- [Structure](#structure)
  * [Table of Contents](#table-of-contents)
  * [Pre-requisite](#pre-requisite)
  * [Data Structure Version - 0.0.0](#data-structure-version---000)
    + [Features](#features)
    + [Detail](#detail)
    + [Example](#example)

## Pre-requisite

Refer to bluetooth [README.md](../bluetooth/README.md) for information on data structure.

## Data Structure Version - 0.0.0

### Features
1. time
2. milliseconds
3. measurement
  1. battery
  2. IMU
  3. sensor
  4. environment

4. value
5. field
  1. ax
  2. ay
  3. az
  4. gx
  5. gy
  6. gz
  7. mx
  8. my
  9. mz
  10. a0
  11. b
  12. temp
  13. hum
  14. alt
  15. v

6. type
  1. acceleration
  2. gyration
  3. magnet
  4. adc
  5. battery
  6. device
  7. velocity (should be computed)

7. host
8. device
9. platform

### Detail

__Time__ is the current time with respects to device location.
__Milliseconds__ is the amount of time elapsed since the start of the session. This value is reset whenever the current session is stopped.
__Measurement__, __value__, __field__, __type__ related to the type of data.
__Host__ is the user name, __device__ is the name of the connected Bluetooth device, and __platform__ is the app information currently being used to assemble the data.

Data is primarily labelled by its measurement, and then further described by the its type. The field is typically an acronym of the type while also containing more specific information on the index, direction, or specification units of the measurement. Generally, it follows:

```c
value
- measurement
  - type
    - field
```

For example, for the X-direction of the acceleration is labelled IMU, then by acceleration, and finally fully described by its field `ax`.

```c
value
- IMU
  - acceleration
    - ax
```

For the sensor data, the field fully describes the index of the sensor `a0`

```c
value
- sensor
  - adc
    - a0
```

Sensors that are over described, for example, are the battery

```c
value
- battery
  - battery
    - b
```


### Example

|time        |milliseconds|measurement|value      |field|type        |host|device |platform|
|------------|------------|-----------|-----------|-----|------------|----|-------|--------|
|15:46:17:290|65          |IMU        |48         |ax   |acceleration|Name|Device1|Android |
|15:46:17:290|65          |IMU        |922        |ay   |acceleration|Name|Device1|Android |
|15:46:17:290|65          |IMU        |-266       |az   |acceleration|Name|Device1|Android |
|15:46:17:353|128         |IMU        |9          |gx   |gyration    |Name|Device1|Android |
|15:46:17:353|128         |IMU        |-2         |gy   |gyration    |Name|Device1|Android |
|15:46:17:353|128         |IMU        |-2         |gz   |gyration    |Name|Device1|Android |
|15:46:17:376|151         |IMU        |1277       |mx   |magnet      |Name|Device1|Android |
|15:46:17:376|151         |IMU        |-5650      |my   |magnet      |Name|Device1|Android |
|15:46:17:376|151         |IMU        |3692       |mz   |magnet      |Name|Device1|Android |
|15:46:17:468|244         |sensor     |158        |a0   |adc         |Name|Device1|Android |
|15:46:17:488|263         |battery    |89         |b    |battery     |Name|Device1|Android |
|15:46:17:533|308         |environment|24.45      |temp |device      |Name|Device1|Android |
|15:46:17:533|308         |environment|32.74      |hum  |device      |Name|Device1|Android |
|15:46:17:533|308         |environment|413.08     |alt  |device      |Name|Device1|Android |
|15:46:19:235|2010        |sensor     |62.93851499|v    |velocity    |Name|Device1|Android |
