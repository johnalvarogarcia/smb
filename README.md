# SMB Connection to Synology and Remote SMB via Tailscale

## Project Overview

At GSR Studios, our recording studio is equipped with a Synology NAS to handle all audio read/write operations in real-time during recording and mixing sessions. This setup ensures efficiency, fault tolerance, and security, leveraging both local and remote SMB connections. We employ Synology Hybrid RAID (SHR), nightly backups, and advanced security measures to maintain the integrity and availability of our data.

## Detailed Description

### Key Components

1. **Synology NAS Configuration**:
   - **Real-Time Audio Operations**: The Synology NAS is crucial for writing and reading audio data in real-time, providing seamless integration with Avid Pro Tools.
   - **Fault Tolerance**: Configured with Synology Hybrid RAID (SHR), similar to RAID 1, to ensure fault tolerance.
   - **Backup Strategy**: Conducts nightly backups to an external HDD and cloud storage to prevent data loss.

2. **SMB Connectivity**:
   - **Local SMB Access**: Facilitates access to Pro Tools sessions via Finder on macOS and Windows Explorer on Windows, and using SMB-multichannel, enhancing workflow efficiency.
   - **Remote SMB Access via Tailscale**: Enables secure remote access to the NAS without opening additional network ports, leveraging Tailscale installed via Docker.

### Process

#### Step 1: Configure Synology NAS for Local Access

1. **Setup Synology NAS**:
   - Install and configure the Synology NAS with SHR for fault tolerance.
   - Create shared folders for storing audio files and Pro Tools sessions.

2. **SMB Configuration**:
   - Enable SMB service on the Synology NAS.
   - Set the minimum SMB protocol to SMB2 to enhance security.
   - Configure user permissions adhering to the principle of least privilege.

3. **Security Measures**:
   - Disable default admin and guest accounts.
   - Enable Adaptive Multi-Factor Authentication (AMFA) for all user accounts.
   - Restrict login attempts to prevent brute-force attacks.
   - Password-protect shared files and set download quantity limits.

4. **Backup and Ransomware Protection**:
   - Schedule nightly backups to both an external HDD and cloud storage.
   - Enable snapshot replication to protect against ransomware attacks.

#### Step 2: Setup Remote SMB Access via Tailscale

1. **Install Tailscale on Synology**:
   - Use Docker to install and configure Tailscale on the Synology NAS.
   - Authenticate and connect the Synology NAS to the Tailscale network.

2. **Configure Remote Access**:
   - Ensure the Synology NAS is accessible remotely through the Tailscale network.
   - Maintain secure access without opening additional ports on the network, reducing exposure to potential threats.

3. **Testing and Verification**:
   - Test SMB access locally via Finder and Windows Explorer to ensure seamless integration.
   - Verify remote SMB access through Tailscale to ensure secure and reliable connectivity.

### Security Best Practices

- **Account Management**:
  - Disable default admin and guest accounts on the Synology NAS.
  - Apply the principle of least privilege to all Synology accounts.

- **Authentication and Access Control**:
  - Enable Adaptive Multi-Factor Authentication (AMFA) for all users.
  - Restrict login attempts to mitigate brute-force attacks.

- **Data Protection**:
  - Use a minimum protocol of SMB2 for all connections.
  - Password-protect shared files and implement download quantity limits.
  - Enable snapshot replication to safeguard against ransomware attacks.

## Conclusion

This setup demonstrates the effective use of a Synology NAS in a professional recording studio environment, ensuring real-time audio operations, fault tolerance, and robust security. By leveraging SMB for local access and Tailscale for secure remote access, we maintain a high level of data integrity and availability. Our security best practices, including multi-factor authentication, least privilege principles, and comprehensive backup strategies, ensure the resilience of our network and data against potential threats.


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
