<h1>How to unbrick Netgear R6220 (my experience)</h1>

<h2>Issue:</h2>

With an incorrect firmware update, I managed to brick my Netgear R6220 router. What I observerd after is that the router would keep rebooting, and would not hava a stable LAN connection with the cable connected (power and LAN1 cable will blink and router would restart).

<h2>What I Tried (but not successful):</h2>

https://kb.netgear.com/000059633/How-do-I-upload-firmware-to-my-NETGEAR-router-using-a-TFTP-client-on-Microsoft-Windows

<h2>What worked (how I unbricked):</h2>

Read a lot of content on unbricking a netgrear router but below videos + recommendation of most articles on nmrpflash utility helped.

<h3>Resources:</h3>
<li>https://www.youtube.com/watch?v=4Nu-bfhsUKE - Helpful video on how to configure the IP v4 address of the LAN connection</li>
<li>https://www.youtube.com/watch?v=ZW5fpOWpI0I&t=746s - Video that the above author cites as a helpful source (related to a TP-Link router</li>
<li>https://github.com/jclehner/nmrpflash/blob/master/README.md - nmrpflash utility and instructions</li>
<li>https://www.netgear.com/support/product/R6220.aspx#download - Latest firmware of R6220</li>

<h3>Steps:</h3>

<ol type="1">
  <li>Turn OFF your router and disconnect the LAN cable</li>
  <li>Install npcap (needed for nmrpflash utility to work)</li>
  <li>Extract nmrpflash to a folder<br>
![image](https://user-images.githubusercontent.com/50511242/164959955-8aea87c7-1640-4c46-a513-f78bd394de68.png)</li>
  <li>Download the latest firmware of Netgear R6220 and save it to the same folder<br>
![image](https://user-images.githubusercontent.com/50511242/164959934-1d1e166b-2aa4-47a2-a75e-1963b02f2474.png)</li>
  <li>Configure the IP address of the lan connection - > Go to legacy control panel network settings to do this (trying to do this from the windows 10 setting panel did not work</li>
  <li>Disable IP v6, and hardcode the 'IPv4 address' as 192.168.1.1 and 'Subnet mask' as 255.255.255.0</li>
  <li>Connect the LAN cable and hold reset button while turning on the router</li>
  <li>Router will start up with in reset mode (LED - Power ON, Wifi/Internet - Blinks alternately, LAN - ON)</li>
  <li>You will see a successful LAN connection in this mode</li>
  <li>Run command prompt as admin and go to nmrp folder</li>
  <li>Type nmrpflash -L to display a list of connections, note the name of the ethernet connection, mine was 'net18'</li>
  <li>Turn the router OFF</li>
  <li>Type command 'nmrpflash -i net18 -f R6220-V1.1.0.112_1.0.1.img'</li>
  <li>The utility will show 'Waiting for ethernet connection'</li>
  <li>Turn the router ON(without reset)</li>
  <li>Connection should succeed and firmware should start uploading</li>
  <li>Wait till the process completes and you will get a message to reboot your device. REBOOT the device</li>
  <li>Reset your LAN network configuration in Windows</li>
</ol>

![image](https://user-images.githubusercontent.com/50511242/164959955-8aea87c7-1640-4c46-a513-f78bd394de68.png)
![image](https://user-images.githubusercontent.com/50511242/164959934-1d1e166b-2aa4-47a2-a75e-1963b02f2474.png)
![image](https://user-images.githubusercontent.com/50511242/164959329-841f4c17-5c61-4469-bf21-55b367c813a1.png)
![image](https://user-images.githubusercontent.com/50511242/164960194-63f684a9-bd1f-4d63-8595-def603fc7ee7.png)
![image](https://user-images.githubusercontent.com/50511242/164960529-e227b38b-85c9-44af-9a3d-32cdf6bb9721.png)


