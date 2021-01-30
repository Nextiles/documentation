# Documentation

- [Documentation](#documentation)
  * [Bluetooth Overview](#bluetooth-overview)
  * [Firmware Version - 0.0.0](#firmware-version---000)
    + [Custom Service](#custom-service)
      - [Delimiter](#delimiter)
      - [Acceleration](#acceleration)
      - [Gyration](#gyration)
      - [Magnetometer](#magnetometer)
      - [ADC](#adc)
      - [Environment](#environment)
  * [Firmware Version - 0.0.1](#firmware-version---001)

## Bluetooth Overview


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
