# NXP MCU Driver

This repository contains a trimmed-down version of NXP's MCUXpresso SDK peripheral drivers for use with MicroPython.

## Overview

This repository follows the structure of the official [NXP MCUX SDK](https://github.com/nxp-mcuxpresso/mcux-sdk) but includes only the driver files needed for supported target chips, reducing the size from approximately 1.6GB to under 100MB.

The repository is designed to be included as a Git submodule in projects like [MicroPython](https://github.com/micropython/micropython) that target i.MX RT and other NXP MCU families.

## Updating to Newer SDK Versions

The `update_sdk.py` script automates updating driver files from the official NXP MCUX SDK releases:

```bash
# Update to the latest SDK release
./update_sdk.py

# Update to a specific release tag
./update_sdk.py --release MCUX_2.16.0
```

The script downloads the specified SDK release, updates existing target chip drivers, and commits the changes to a new branch.

## Adding Support for New Chips

To add a new target chip:

1. Create an empty folder with the chip name in `sdk/devices/`
2. Run `./update_sdk.py` to populate it with drivers from the latest SDK

The automation tool will detect the new target and include it in future updates.

## Current SDK Version

The current SDK version is stored in `sdk/version.txt`.

## History

This repository was originally maintained at [hathach/nxp_driver](https://github.com/hathach/nxp_driver) as part of the TinyUSB project. When TinyUSB migrated to using the official NXP SDK directly, this trimmed version was forked to the MicroPython organization to continue serving projects requiring a smaller dependency footprint.

