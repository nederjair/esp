1. Start a Project

- enter the esp folder

```bash
cd ~/esp
```
- copy a base project from the get-started folder

```bash
cp -r $IDF_PATH/examples/get-started/hello_world .
```

2. Compile the program for your device

- enter the copied base project folder

```bash
cd ~/esp/hello_world
```

- set ESP32-C6 as the target

```bash
idf.py set-target esp32c6
```

- run the project configuration utility

```bash
idf.py menuconfig
```

- get out of the menu pressing `esc`

3. Build the Project

```bash
idf.py build
```

4. identify the port

check the ports before connecting the esp32

```bash
ls /dev/tty*
```

- connect the esp32

- check the ports with the esp32 conected and the port that appears is the esp32 port name

```bash
ls /dev/tty*
```

5. upload the compiled program to your device

```bash
idf.py -p PORT flash
```
