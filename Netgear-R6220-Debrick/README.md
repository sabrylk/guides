<h1>How to debrick Netgear R6220 (my expericence)</h1>

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
<li>https://www.netgear.com/support/product/R6220.aspx#download - Latest firmware of NR6220</li>

<h3>Steps:</h3>

<ol type="1">
  <li>Install npcap (needed for nmrpflash utility to work)</li>
  <li>Extract nmrpflash to a folder</li>
  ![image](https://user-images.githubusercontent.com/50511242/164959955-8aea87c7-1640-4c46-a513-f78bd394de68.png)
  <li>Download the latest firmware of Netgear R6220 and save it to the same folder</li>
  ![image](https://user-images.githubusercontent.com/50511242/164959934-1d1e166b-2aa4-47a2-a75e-1963b02f2474.png)

</ol>

![image](https://user-images.githubusercontent.com/50511242/164959329-841f4c17-5c61-4469-bf21-55b367c813a1.png)
