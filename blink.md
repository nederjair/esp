## 1. Start a the blink project

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
cp -r $IDF_PATH/examples/get-started/blink/ .
```

## 2. Compile the program for your device

### 2.1. enter the copied base project folder

```bash
cd ~/esp/blink/
```

### 2.2.  set ESP32-C6 as the target

```bash
idf.py set-target esp32c6
```

### 2.3. run the project configuration utility

```bash
idf.py menuconfig
```

### 2.4. Set the type of LED to use, in this case we set it to GPIO.


### 2.5. set the GPIO pin number where the LED is located to 15. The LED of XIAO ESP32C6 is connected to GPIO15. 

### 2.6. set the period of the LED in ms

### 2.7. save the configuration pressing `s`

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
