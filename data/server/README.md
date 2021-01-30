# Database

## Table of Contents

- [Database](#database)
  * [Table of Contents](#table-of-contents)
  * [Pre-requisite](#pre-requisite)
  * [Variables](#variables)
  * [Hierarchy](#hierarchy)
    + [Example](#example)

## Pre-requisite

Refer to data=structure [README.md](../data-structure/README.md) for information data structure and organization.

## Variables

1. User name
2. User association: team, league, organization, unaffiliated
3. User connection: coach, other players, etc.
4. Primary sport
    1. Secondary sport
5. Type of exercise
    1. Primary exercise (could be fluid)
    2. Secondary exercise
6. Day of use
7. Time of use

## Hierarchy

- Bucket
  - Type of user
    - User name
      - Data (YYYY-MM-DD)
        - Time (of the transmitting device)

### Example

Flatten

```bash
/nx-bucket/User/anonymous/2021-01-0X/01:23:45
/nx-bucket/User/anonymous/2021-01-0X/12:34:56
/nx-bucket/User/anonymous/2021-01-0X/23:45:67
/nx-bucket/User/anonymous/2021-01-1X/01:23:45
```

Tree

```bash
/nx-bucket
  - /User
    - /anonymous
        -/2021-01-0X
          - /01:23:45
          - /12:34:56
          - /23:45:67
        -/2021-01-1X
          - /01:23:45
```
