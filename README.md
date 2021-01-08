****EXALEAP SEMICONDUCTOR Pvt Ltd, BLR_IN****
--------------------------------------

#### Base Image For Freedom U540 Hi-five Unleashed

Kernel Version: v5.5.6

![alt text](https://images.prismic.io/sifive/6320ea644480fdb6131b9d63eae826b7a1e1dca9_boards_unleashed.jpg?auto=compress,format)

####Download the Image by clicking on this URL: https://exaleap-storage.s3.ap-south-1.amazonaws.com/public/core-image-base-exaleapsemi-20201230113707.rootfs.wic.gz

**System Requirements**
--------------------------------------
step 1: Please install minicom on your host machine. The following command install minicom on Ubuntu distribution

$ `sudo apt-get install minicom`

step 2: After installing open minicom, set the serial port to USB '0' or '1' and set the baud rate at 115200 and          click on save

step 3: Wait until your image reboots

$ `sudo minicom -s`

- Enter the serial device /dev/ttyUSBX by pressing ‘a’ and then pr

- Press Enter.

- Turn off the hardware flow control by pressing ‘f’

- Press enter to save

- Select save setup as default

- Exit.


**Dumping Image on to SD Card**
--------------------------------------

1, Ensure to use minimum 64GB SD card and make zero partition using the format tool or gparted tool.

2, Insert SD card in the Card reader.

3, Using zcat tool copy the image into SD card.

4, Using dd tool copy the image into SD card.
   The output of a “freedom-u540”  build will be a “<image>.wic.gz” file. You can write this file to a SD card usi   ng:

	`$ zcat <image> <machine>.wic.gz | sudo dd of=/dev/sdX bs=4M iflag=fullblock oflag=direct conv=fsync status=progress` 

5, Replace ( <image> <machine>.wic.gz )  with your image file. And replace  sdX with sd card name.
   By using lsblk check your sd card name. Could be “sdb,sdc...”

6, copying your image into the SD card. After copying the image, remove SD card from the card reader.

7, Insert SD card into your Target Board and supply the power.


##### For more details, Please reach out to contact@exaleapsemi.com
