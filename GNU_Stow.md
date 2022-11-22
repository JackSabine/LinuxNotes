# GNU Stow

Target (TAR): the directory in which symlinks should be recursively created
- This is where you want files to _appear_ to be installed
- Specified with `-t` or `--target=`

Directory (DIR): the directory where symlinks can be recursively found
- These are the binaries are _actually_ installed
- Specified with `-d` or `--dir=`

## Examples

### Create symlinks in ~/ for files in the current directory

The terminal dot indicates that stow should parse packages found in DIR (and not DIR itself).

`stow -t ~/ .`
DIR here is implied as the current working directory where this command is called.
If this snippet occurs in a script, it uses the CWD of the script's caller (not the script itself).

### Create symlinks for files in /opt/Xilinx/Vivado/2022.1/bin to /opt/bin

`sudo stow -t /opt/bin/ -d /opt/Xilinx/Vivado/2022.1/bin/ .`

### Remove the symlinks from the previous section 

`sudo stow -D -t /opt/bin/ -d /opt/Xilinx/Vivado/2022.1/bin/ .`



