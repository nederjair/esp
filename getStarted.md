## 1. Start a Project

### 1.1. enter the esp folder

```bash
cd ~/esp
```

### 1.2. set the environment variables

```bash
get_idf
```


### 1.2. copy a base project from the get-started folder

```bash
cp -r $IDF_PATH/examples/get-started/hello_world .
```

## 2. Compile the program for your device

### 2.1. enter the copied base project folder

```bash
cd ~/esp/hello_world
```

### 2.2.  set ESP32-C6 as the target

```bash
idf.py set-target esp32c6
```

### 2.3. run the project configuration utility

```bash
idf.py menuconfig
```

### 2.4. get out of the menu pressing `esc`

## 3. Build the Project

```bash
idf.py build
```

## 4. identify the port

### 4.1. check the ports before connecting the esp32

```bash
ls /dev/tty*
```

### 4.2. connect the esp32

### 4.3. check the ports with the esp32 conected and the port that appears is the esp32 port name

```bash
ls /dev/tty*
```

## 5. upload the compiled program to your device

```bash
idf.py -p PORT flash
```

## 6. monitor the output

to check if "hello_world" is indeed running, type 

```bash
idf.py -p PORT monitor 
```

**get out from the monitor pressing `ctrl + ]`**

(Do not forget to replace PORT with your serial port name). This command launches the IDF Monitor application.

# Troubleshooting

##  Could not open port <PORT>: Permission denied: '<PORT>'
The currently logged user should have read and write access the serial port over USB. On most Linux distributions, this is done by adding the user to dialout group with the following command:
```bash
sudo usermod -a -G dialout $USER
```

on Arch Linux this is done by adding the user to uucp group with the following command:

```bash
sudo usermod -a -G uucp $USER
```
