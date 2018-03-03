# PUBG-Radar
By sniffering UDP packets...

Written in Kotlin.

# Build
Using [Maven] (https://maven.apache.org/)

# Linux
If you experienced `X Error of failed request:  RenderBadPicture (invalid Picture parameter)` on Linux build, try switch to branch `linux`. Run with arguments `<ip_to_sniff> <PortFilter|PPTPFilter> [target_ip]`

# VMWare or Middle PC Setup
Here is an easy way using `arpspoof` to redirect packets from your Game PC to a Middle PC.

# Make sure your VMWare instance or Middle PC is in the same LAN as your Game PC

Execute the following commands on the VMWare or Middle PC: 
1. run `sudo apt-get install dsniff` to install `arpspoof`.
2. edit `/etc/sysctl.conf`. add/uncomment `net.ipv4.ip_forward=1`. save and run `sudo sysctl -p` to enable ip_forward.
3. run `sudo arpspoof -i <eth_interface_name> -t <game_pc_ip> <router_ip>` to spoof Game PC.
4. run `sudo arpspoof -i <eth_interface_name> -t <router_ip> <game_pc_ip> ` to spoof Router.
5. run `sudo java -jar pubg-radar-with-dependencies.jar <middle_pc_ip> <PortFilter|PPTPFilter> <game_pc_ip>`

Also Windows version included, don't ask for future updates...
And use your own map.
