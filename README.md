# Documentation

## Table of Contents

- [Documentation](#documentation)
  * [File Naming Convention](#naming-convention)
  * [Repository Naming Convention ](#categories)
    + [Device](#device)
    + [Data](#data)
    + [Mobile](#mobile)
    + [Client Specific](#client-specific)
    + [Company Specific](#company-specific)
    + [Generators](#generators)
    + [Forked](#forked)
  * [Branching](#branching)
  * [Development Methodoloy](#development-methodoloy)
  * [References](#references)

## File Naming Convention

Category hierarchies are concatenated to form the repo name going from general category to more specific, hyphenated-between-words, and all in lower case. There should be no plural in these categories, such as device~~s~~, app~~s~~, web~~s~~, etc.

For example, creating a mobile app in iOS for production purposes will be named. Note that iOS is _not_ capitalized.

```
mobile-ios-internal
```

## Repository Naming Convention

Each repo will be named based on their category, with hyphenated suffixes to further describe their project information. An example would be

```
device-pcb
```

which describes that this repo belongs to the device team, members who are responsible for developing the PCB (printed circuit board), for the group.

### Device
- `device`
  - [`firmware`](https://github.com/Nextiles/device-firmware) - device firmware machine code
  - [`pcb`](https://github.com/Nextiles/device-pcb) - printed circuit board schematics
  - [`techpack`](https://github.com/Nextiles/device-techpack) - vector files for textile and sensor layout
  - [`testing`](https://github.com/Nextiles/device-testing) - scripts and quality-control code to test devices
  - [`demo`](https://github.com/Nextiles/device-demo) - scripts and frontend/backend code to demonstrate device functionality

### Data
- `data`
  - [`lab`](https://github.com/Nextiles/data-lab) - cookie-cutter data exploration code for machine learning or algorithm development
  - [`cloud-manager`](https://github.com/Nextiles/data-cloud-manager) - scripts and CLI revolved around remote cloud management on AWS, Firebase, Influx, etc.

### Mobile
- `mobile`
  - `ios`
    - [`production`](https://github.com/Nextiles/mobile-ios-production)
    - [`internal`](https://github.com/Nextiles/mobile-ios-internal)
    - [`testing`](https://github.com/Nextiles/mobile-ios-testing)
  - `android`
    - [`production`](https://github.com/Nextiles/mobile-android-production)
    - [`internal`](https://github.com/Nextiles/mobile-ios-internal)
    - [`testing`](https://github.com/Nextiles/mobile-android-testing)
  - `reactnative`
    - [`testing`](https://github.com/Nextiles/mobile-reactnative-testing)

### Client Specific
- `client`
  - `XYZ` - client name, documents, code, custom development revolved around a client product

### Company Specific
- `nextiles.github.io` - github pages website hosting, with related subdomains
  - [`patents`](https://github.com/Nextiles/patents) - public list of patents
  - [`trademark`](https://github.com/Nextiles/trademark) - public list of trademarks
  - [`whitepaper`](https://github.com/Nextiles/whitepaper) - business and technology whitepapers
  - [`slides`](https://github.com/Nextiles/slides) - company slide decks
- `brand`
  - [`assets`](https://github.com/Nextiles/brand-assets) - brand logos, colors, fonts, images
- [`documentation`](https://github.com/Nextiles/documentation)

### Generators
- `generator` - to be made

### Forked
- [`gitignore`](https://github.com/Nextiles/gitignore)
- [`InfluxData-Swift`](https://github.com/Nextiles/InfluxData-Swift)

## Branching

Branches with feature requests should have names starting with the contributor's initials, the feature name, and any other optional notes such as the development environment. Note that all branches should be lowercased, and hyphenated between words. For example

```
gls-newfeature-linux
```

## Development Methodoloy

To be created

## References
- Development strategy - https://github.com/rotati/wiki/wiki/Deployment-and-QA-Workflow
- Wiki structure and format - https://github.com/snowplow/snowplow/wiki
