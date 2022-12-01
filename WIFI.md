# Setting up WIFI for `pathetique`

[Broadcom Wireless Drivers help forum](https://askubuntu.com/a/60395)

## Motivation

Pop!\_OS does not come with a "Device Drivers" GUI like Ubuntu, so this driver must be installed manually

## Using the above forum

* Installation has only required steps 1-3 (forum) in the past
* Ensure no wireless driver is found or present on the system
  * This includes a package like `bcmwl-kernel-source`
  * Remove with `sudo apt purge <wireless driver pkg>`

1. Use `lspci -nn -d 1434:` (with the colon, too) to determine which PCI.ID your WIFI module appears as
   * Note the "(rev xx)" along with the PCI.ID if it appears after
   * Example output: `06:00.0 Network controller [0280]: Broadcom Inc. and subsidiaries BCM4352 802.11ac Wireless Network Adapter [14e4:43b1] (rev 03)`

2. `sudo apt update`
3. `sudo apt-pciids`

4. Index the table provided on the forum in step 3 with your PCI.ID (and revision number if present) for the apt pkg to install
   * The entry for the PCI.ID in step 1 (`14e4:43b1 rev 03`) on Ubuntu 20.04 (and later) specifies `bcmwl-kernel-source`

5. `sudo apt install <package from step 4>`
   * The forum also suggests installing `linux-firmware`, but this was already installed with Pop!\_OS
6. `sudo reboot`
 
