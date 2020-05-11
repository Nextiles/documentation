# Documentation

## Categories

### Device
- device
  - firmware - contains C code
  - PCB - circuit schematics
  - 3D - casings and device renderings
  
### Data
- data
  - lab - playground for any type of prototyping
  - <name> - repo pertaining to a specific project name

### Mobile
- mobile
  - ios
    - internal
    - demo
      - <name>
  - android
    - internal
    - demo
      - <name>

### Web
- web
  - internal
  - demo
  
### Generators
- generator
  - nx-datalab
  - nx-ble - drafting a quick bluetooth platform
  - nx-demos - this can consist of spinning up ios, android, or web demos via subgenerators
  
### Public
- nextiles.github.io
- documentation - will also contain the wiki page

## Naming conventions

Category heirarchies are concatenated to form the repo name, all in lower case.

For example, creating a mobile ios for internal purposes will be named
> mobile-ios-internal

Another would be, creating devices with 3D parts will be named
> device-3D

There should be no plural in these categories, such as device~~s~~, app~~s~~, web~~s~~, etc.

## Branching

Branches with feature requests should have names starting with the contributor's initials, the feature name, and any other optional notes such as the development environment.

Note that all branches should be lowercased, and hyphenated between words. For example

> gls-newfeature-linux

### Development cycles

`Development` > `Staging` > `Production` ~ `Stable`

Development = any type of testing, feel free to sandbox
Staging = ... 
Production = ...
Stable = ...

## References
- https://github.com/rotati/wiki/wiki/Deployment-and-QA-Workflow
