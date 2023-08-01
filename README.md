# Flashing Xiaomi Router Flash Memory using Neoprogrammer and CH341A flasher



  # Windows

  Download firmware; | Stock Firmware | Openwrt | X-WRT | 


  https://drive.google.com/drive/folders/1-XOLDLbs5zxp0DNDm0xBgcn5iUWfvwXc?usp=drive_link


  Neoprogrammer 2.1.0.10 download link: https://drive.google.com/file/d/15SwiXn7tV8QSkxxueQNKGZabhwdOGU28/view?usp=drivesdk
   
  Drivers: https://drive.google.com/drive/folders/1MzpA0rRrLcBTUIOpg0YtSNExIpj4wwqU?usp=drive_link

  Steps: connect ch341a clip to 4c router IC, open neoprogrammer and detect the chip select the router IC, read the IC, erase the ic, load the 16mb firmware 
  (stock or openwrt) then write IC click yes and wait and start configure your router



![image](https://github.com/xiv3r/Xiaomi-Router-4C-CH34A-flash-firmware/assets/117867334/704a2efb-d911-4737-8670-8480cfe073e0)


![IMG_20230723_083113](https://github.com/xiv3r/Xiaomi-Router-4C-CH34A-flash-firmware/assets/117867334/8c399a16-f7a1-4e77-b900-d4bfa674f79d)


![IMG_20230723_083150](https://github.com/xiv3r/Xiaomi-Router-4C-CH34A-flash-firmware/assets/117867334/bf2053cc-a585-41b9-b8a0-b150ddcbd87e)


![image](https://github.com/xiv3r/Xiaomi-Router-4C-CH34A-flash-firmware/assets/117867334/32c84a15-dd5d-43b0-87b1-6be5aeccad41)

![image](https://github.com/xiv3r/Xiaomi-Router-4C-CH34A-flash-firmware/assets/117867334/76807418-5626-4829-a0f4-aebe305701ba)
![image](https://github.com/xiv3r/Xiaomi-Router-4C-CH34A-flash-firmware/assets/117867334/5621d78b-b314-4ba8-8fec-1badffd65141)

red wire must be connected to this pin 1 (dot) in chip

![image](https://github.com/xiv3r/Xiaomi-Router-4C-CH34A-flash-firmware/assets/117867334/466c5aad-61c9-498a-bd1e-c9171fe64c86)

![image](https://github.com/xiv3r/Xiaomi-Router-4C-CH34A-flash-firmware/assets/117867334/dd03fa11-4b8d-47f5-b878-eb790ec73332)




# For Linux
   
   CH341a Driver: [driver.zip](https://github.com/xiv3r/Xiaomi-Router-4C-CH341A-flasher/files/12224825/driver.zip)
 
   Driver installation:
         extract the driver.zip and open your root terminal then drop the unzip driver folder to the terminal or manually locate the driver like cd 
  /home/(name)/driver

![Screenshot_20230801_132017](https://github.com/xiv3r/Xiaomi-Router-4C-CH341A-flasher/assets/117867334/fc367842-6724-4f66-80a5-6409bd93190b)

   Execute root terminal type:

    sudo make && sudo make install

# Flashing using flashrom
 
  First Backup eeprom dump firmware:

    flashrom -VV --programmer ch341a_spi -r backup.bin 

  Flash new dump firmware:

    flashrom -VV --programmer ch341a_spi -w /home/user/Downloads/backup.bin
