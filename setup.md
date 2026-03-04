# Setup Verilog development environment on MacOS
## Install homebrew 
To install homebrew, run the following command in your terminal
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
## Install icarus-verilog
Icarus-verilog is an open source compiler and simulator for the Verilog Hardware Development Language. You can install it through homebrew using the following command
```
brew install icarus-verilog
```
## Install GTKWAVE
For more information, refer to https://github.com/gtkwave/gtkwave
### Install dependencies 
The following command installs dependencies required for GTKWAVE 
```
brew install desktop-file-utils shared-mime-info       \
             gobject-introspection gtk-mac-integration \
             meson ninja pkg-config gtk+3 gtk4
```
### Build GTKWAVE
```
git clone "https://github.com/gtkwave/gtkwave.git"
cd gtkwave
meson setup build && cd build && meson install
```
## Text Editor
I use Visual Studio Code as my text editor for VHDL. You may use any text editor you like, however, VSCode is more convienent for analysis.
### Plugins
WaveTrace by wavetrace. This is essential (unless you have time to mess around) as it enables you to directly view waveforms from vcd files within VSCode. \
VerlogHDL/SystemVerilog/Bluespec SystemVerilog by Masahiro Hiramori.\
Verilog HDL by leafvmaple (seems redundant, but i found it easier with the green compile button). \
Verilog_Testbench by Truecrab. 

