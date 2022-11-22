# Vivado

## If installed in /opt/Xilinx and want to add to PATH

1. `sudo stow -t /opt/bin/ -d /opt/Xilinx/Vivado/XXXX.Y/bin/ .`
   (For Vivado version `XXXX.Y`)
2. Add `/opt/bin` to PATH in your favorite manner
   * Can add to path in `/etc/environment`, `/etc/profile`, `~/profile`

## If hardware not detected

Potential solution: need to install cable drivers for talking to any Xilinx FPGA dev board.

Source the script (in your Vivado install dir): `data/xicom/cable_drivers/lin64/install_script/install_drivers/install_drivers`

[Forum link](https://support.xilinx.com/s/question/0D52E00006iHuoHSAS/hardware-target-not-detected-vivado-20172?language=en_US)

## Where to find constraints file for Basys3

1. [Clone the Basys3 repository](https://github.com/Digilent/Basys3)
2. Copy `Basys3_Master.xdc` from `Resources/XDC` to your project

