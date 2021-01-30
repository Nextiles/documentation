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

Bluetooth devices have sets of services which carry sets of characteristics which represent the data packages of that service. For example, the battery service has UUID `180F` which is discovered upon Bluetooth connection. Subscription or read of the underlying battery characteristic with UUID `2A1B` provides the appropriate battery value in hex.

There are standard Bluetooth services which have distinct UUIDs, and custom characteristics which can be generated from a random mixture of 128-bits. UUIDs can be made through UUID generators such as [this one](https://www.uuidgenerator.net/). Hierarchically, the service characteristic schema can be visualized as a stack.

```
- peripheral
  - service1
    - characteristic1
      - value
      - descriptor
  - service2
    - characteristic1
      - value
      - descriptor
    - characteristic2
      - value
  - service3
    - ...
  - ...
```

Characteristics can have one or more descriptors that can be read and updated by the peripheral or from the central device.

Bluetooth sniffers
- Android - [nRF Connect](https://play.google.com/store/apps/details?id=no.nordicsemi.android.mcp&hl=en_US&gl=US)
- iOS - [nRF Connect](https://apps.apple.com/us/app/nrf-connect-bluetooth-app/id1054362403)
- Company custom scripts - [device-testing/bluetooth](https://github.com/Nextiles/device-testing/tree/master/bluetooth)

## Firmware Version - 0.0.0

1. DFU
2. Device information
  - Manufacture name
  - Model number
3. Battery
  - Battery level
4. Custom service
  - Acceleration
  - Gyration
  - Magnetometer (direction)
  - ADC (force)
  - Environment

### Custom Service

#### Delimiter

`,` - value delimiters within a characteristic are represented by a comma

#### Acceleration

Values are multiplied by 100 to remove decimal places.

```c
±XXXXX,±YYYYY,±ZZZZZ
```

#### Gyration

Values are multiplied by 100 to remove decimal places

```c
±XXXXX,±YYYYY,±ZZZZZ
```

#### Magnetometer

Values are not multiplied, values typically are wholenumbers

```c
±XX.XX,±YY.YY,±ZZ.ZZ
```

#### ADC

Values are 10 bit (1023) to 12 bit (4095) meaning 4 bytes of resolution when casted to chars. Every characteristic packet can carry up to 5 x 4 byte sensor values.

```c
AAAABBBBCCCCDDDDEEEE
```

This firmware version only contains 1 sensor, index `[4]` and beyond are random values which should be trimmed.

```c
AAAA
```

#### Environment

Index one is the temperature, index 1 is the humidity, and index 3 is the barometer (altitude) which can be a positive or negative value.

```c
XXX.XX,YYY.YY,±ZZ.ZZ
```

## Firmware Version - 0.0.1

1. DFU
2. Device information
  - Manufacture name
  - Model number
3. Battery
  - Battery level
4. Custom service
  - Acceleration
  - Gyration
  - Magnetometer (direction)
  - ADC (force)
  - Environment
