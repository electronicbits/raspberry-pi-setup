# raspberry-pi-setup
Steps to get raspberry pi configured 

![alt text](https://raw.githubusercontent.com/electronicbits/raspberry-pi-setup/master/Raspberry-Pi-3.jpg)

## Getting the headless raspberry up and running:

- Download raspbian lite from here:
https://www.raspberrypi.org/downloads/raspbian/

- Use a software like "win32diskimager" (if using Windows) to burn the .img file into a sd card

- Once the image has finished burning, create an empty file called ssh in the root directory.

- Additionally, use the "wpa_passphrase" tool to generate network string specifications and psk.

- Create a file called wpa_supplicant.conf. Copy the results of the step 4 inside the file, and the following:

`
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=AU
`

- The file should look like this

`
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=AU

network={
        ssid="SP1"
        #psk="<thepasswordtomynetwork>"
        psk=5a6dad56abe2df56b413cbea856796fbca12ca50b1998667fd838039187c2de
}
`

The psk value, is the encrypted password. Remember to remove the psk with your actual password.
