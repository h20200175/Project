# Driver writing for I2C interfacing of ADXL745 sensor

# Prerequisite for the project
  For these files to run we need raspberry pi running on linux kernel. To update and build the kernel use [link](https://www.raspberrypi.com/documentation/computers/linux_kernel.html). First remove the loaded module. 
  Command to remove the module is "sudo rmmod adxl.ko" 
  
  List of softwares used for this project's implementation:
  1. Putty
  2. WinSCP
  3. Vnc viewer
 
# Summary
  The aim of this project to write a driver to read the data from ADXL745 sensor interfaced using I2C protocol to raspberry pi 4 (1GB). ADXL745 ... to be added
  
# Introduction  
  I2C stands for Inter-Integrated Circuit.I2C protocol is widely used for interfacing peripheral devices. I2C is a two wired protocol with one wire as "SCL" used for carrying       clock signal and other wire is "SDA" used for transferring data serially. I2C is a master slave protocol which means that the communication will always be initiated by the         master and in total we can connect 128 slaves.
  ..... to be added
  
  
# Hardware
  
   ... image
  
  Hardware consists of RaspberryPi 4 and ADXL745 sensor.
  
# The I2C interface
  

# Kernel Driver
  

# Schematic 
  ![image](https://user-images.githubusercontent.com/91187808/145357407-c39e79d1-9e30-4f4d-bb4e-ba7854d7fe6a.png)

  ADXL745 can be connected to any available "SDA" and "SCL" lines of raspberryPi 4 board that can be identified from the GPIO pin assignment and GPIO alternate functionality       table of [RaspberryPi 4 datasheet](https://datasheets.raspberrypi.com/rpi4/raspberry-pi-4-datasheet.pdf). 
  Following is the GPIO pin assignment diagram.
  
  ![image](https://user-images.githubusercontent.com/91187808/145344539-5158935a-cb20-44bf-bc89-94835e4d2372.png)
  
  Connection Table:
  
  | ADXL Pin | RaspberryPi Pin |
  | --- | --- |
  | VCC | Pin 1 (3.3 V)|
  | Ground | Pin 39 |
  | SCL | Pin 3 |
  | SDA | Pin 5|
  
 # Use Instructions
   1. Connect the sensor according to the schematic diagram or connection table and connect the RaspberryPi 4 board using ethernet cable.
   2. Open putty and connect to the board using Hostname or IP address.![image](https://user-images.githubusercontent.com/91187808/145359917-9f3e5310-ddf1-442f-b191-c72cf7c452ca.png)
   3. Login using username: pi and password: raspberry. ![image](https://user-images.githubusercontent.com/91187808/145360147-afe4627f-dc61-4708-a586-c68ff15f9d0c.png)
   4. Once you are inside the pi board access your folder using putty terminal. For creating and moving file from host computer to RaspberryPi 4 board one can use [WinSCP](https://winscp.net/eng/download.php).
   5. Winscp Terminal will look like:![image](https://user-images.githubusercontent.com/91187808/145360719-025f612f-0c51-450d-a408-77375727b1a1.png)
   6. Compile all the files using "make" command.
   7. Insert the module to kernel using command "sudo insmod adxl.ko".
   8. Check if the module is correctly inserted using command "lsmod".
   9. Give the rights to the user to open the device file using command "sudo chmod 777 /dev/adxl".
   10. Run the userspace program using command "./usrapp".
   11. If there is no error you will be able to see the sensor reading.![image](https://user-images.githubusercontent.com/91187808/145360991-494f856e-31d4-479a-8653-1f0aff9daae9.png)
   
   
 
  
 
  

  
   
  
  
