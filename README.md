# Umacchanger

## What is it?
  Umacchanger is a knock-off python script of the original macchanger program. It is not as powerful as the original macchanger program as it has only 3 of its functions (-r, -m and -p). Those three options I use the most, so I only coded those three options. 
  
  
## Why Umacchanger
  Because I'm lazy! When using macchanger program to alter the mac address of an interface, you'll have to run through three steps
  - Bring down the network inteface you want to change (using ifconfig) 
  - Use the macchanger program to actually change the interface's mac address 
  - Bring the network interface up again (using ifconfig as well)

  That's 3 steps just to get the job done. And if your system's NetworkManager is configured to be crazy (and it's most likely is), any change in network or reconnection that occurs on that interface would cause NetworkManger to undo any modifications you've made to that interface. You can of course stop this behavior by killing the NetworkManager before changing the mac address but it introduces another step in changing the maccaddrss, bad news for us lazy folks :( For someone who frequently hops from random address to random address or to a specific mac this is quite irritating to do.
  
 
 ## How To Use
 Umacchanger automates every step needed in changing an interface's mac address. So you only need to supply it arguments.
 
 Assuming our interface is wlan0
 - For a random mac address 
  ```
  Umacchanger -r wlan0 
  ```
  
 - For a specific mac address e.g 00:11:22:33:44:55
 ```
 Umacchanger -m 00:11:22:33:44:55 wlan0
 ```
 
 - To set an interface back to it's burned in mac address (it's default address)
 ```
 Umacchanger -p wlan0
 ```
 
 
 ## Issues
 This script doesn't come with a dependency checker. Meaning you'll have to make sure the below commands are installed on your distro
 - ifconfig
 - NetworkManager or network-manager (depending on your os)
 - Python3
 
 You can always fork around add one if you want.
