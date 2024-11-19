1. Install Prerequisites

```bash
sudo pacman -S --needed gcc git make flex bison gperf python cmake ninja ccache dfu-util libusb
```

2. Get ESP-IDF

```bash
mkdir -p ~/esp
```

```bash
cd ~/esp
```

```bash
git clone -b v5.3.1 --recursive https://github.com/espressif/esp-idf.git
```

3. Set up the Tools

```bash
cd ~/esp/esp-idf
```

```bash
./install.sh esp32c6
```

4. Set up the Environment Variables

The installed tools are not yet added to the PATH environment variable. To make the tools usable from the command line, some environment variables must be set. ESP-IDF provides another script which does that.

- Copy and paste the following command to your shell's profile (.profile, .bashrc, .zprofile, etc.)

```bash
alias get_idf='. $HOME/esp/esp-idf/export.sh'
```
- source the bash

```bash
source ~/.bashrc
```
