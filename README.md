<h1>SMB Connection to Synology And Remote SMB via Tailscale</h1>


<h2>Description</h2>
My recording studio, GSR Studios, is configured to run all audio off of a Synology NAS. The Synology is used to write and read audio in realtime during recording and mixing sessions, and is configured in SHR (similar to Raid 1) for fault tolerance, along with a nightly backup to both an external HDD and cloud storage.
<br>
<p></p>
We mainly connect via SMB which allows our Synology NAS to give us access to all of our Avid Pro Tolls sessions via Finder or Windows Explorer.
<p></p>
Additionally, we can use Tailscale, installed and configured via Docker, to authenticate and use SMB remotely without having to open additional ports on the network.

<p></p>
To keep our network secure we:
<ul>
  <li>Disable the default admin and guest accounts on our Synology NAS.</li>
  <li>Use leat privilege principles on our Synology accounts.</li>
  <li>Enable Adapdtive Multi-Factor Authenticaion for all users.</li>
  <li>Restrict login attempts.</li>
  <li>Use a minimum protocol of SMB2.</li>
  <li>Password protect shared files along with download quantity limits to protect confidentiality.</li>
  <li>Use snapshot replication for ransomware protection.</li>
</ul>
<br />


<h2>Platforms and Technologies Used</h2>

- <b>Network Attached Storage (NAS)</b> 
- <b>SMB</b>
- <b>Tailscale</b>
- <b>Docker</b>
- <b>Pihole</b>
- <b>Synology DSM</b>
- <b>Synology QuickConnect

<h2>Netowrk Diagram</h2>

<p align="center">
 <br/>
<img src="https://i.imgur.com/gjyj3AS.jpeg" height="80%" width="80%"/>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
