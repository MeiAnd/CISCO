## Operating System Security

**What does an organization need to do to harden an operating system and keep it secure?**


**Good Administrator:** Configure the operating system to protect against outside threats.That means 

* removing any unnecessary programs and services
* making sure that security patches and updates are installed in a timely manner to correct faults and mitigate risks.

**A systematic approach**

It’s important to have a systematic approach in place for addressing system updates. An organization should:

* establish procedures for monitoring security-related information
* evaluate updates for applicability
* plan the installation of application updates and patches
* install updates using a documented plan.

**A baseline**

Another critical way to secure an operating system is to identify potential vulnerabilities. To do this, establish a baseline to compare how a system is performing against baseline expectations.


### Patch Management

Cybercriminals work relentlessly to exploit weakness in computer systems. To stay one step ahead, keep systems secure and up to date by regularly installing patches.

**What do you need to do?**

As a cybersecurity professional, it’s good practice to test a patch before deploying it throughout the organization. A patch management tool can be used to manage patches locally instead of using the vendor’s online update service.

An automated patch service provides administrators with a more controlled setting:

* Administrators can approve or decline updates.
* Administrators can force the update of systems on a specific date.
* Administrators can obtain reports on the update(s) needed by each system.
* There is no need for each computer to connect to the vendor’s service to download patches; instead, it gets the verified update from a local server.
* Users cannot disable or circumvent updates.


## Endpoint Security

A host-based solution is a software application that runs on a local device (or endpoint) to protect it. The software works with the operating system to help prevent attacks.

**Host-Based Firewall:** : A host-based firewall runs on a device to restrict incoming and outgoing network activity for that device. It can allow or deny traffic between the device and the network. The software firewall inspects and filters data packets to protect the device from becoming infected. 

**Host Intrusion Detection System (HIDS)**: HIDS software is installed on a device or server to monitor suspicious activity. It monitors system calls and file system access to detect malicious requests. It can also monitor configuration information about the device held in the system registry.

**Host Intrusion Prevention System (HIPS)**: HIPS is software that monitors a device for known attacks and anomalies (deviations in bandwidth, protocols and ports), or finds red flags by assessing the actual protocols in packets. If it detects malicious activity, the HIPS tool can send you an alarm, log the malicious activity, reset the connection and/or drop the packets.

**EndPoint detection and response (EDR):** EDR is an integrated security solution that continuously monitors and collects data from an endpoint device. It then analyzes the data and responds to any threats it detects. An antivirus can only block against threats, while EDR can do that and find threats on the device. e.g **BitDefender**

**Data Loss Prevention (DLP):** DLP tools provide a centralized way to ensure that sensitive data is not lost, misused or accessed by unauthorized users.
e.g

* McAfee DLP
* Trend Micro
* Sophos

**NextGen Firewall** : NGFW is a network security device that combines a traditional firewall with other network-device-filtering functions. For example, an application firewall using in-line deep packet inspection (DPI) on an intrusion protection system (IPS).

* Palo Alto
* Fortinet
* Cisco


## Encryption

 Is a tool used to protect data. Encryption uses a complicated algorithm to transform data and make it unreadable.

**Host Encryption**: The Windows Encrypting File System (EFS) feature allows users to encrypt files, folders or an entire hard drive. Full disk encryption (FDE) encrypts the entire contents of a drive (including temporary files and memory). Microsoft Windows uses BitLocker for FDE.

To use BitLocker, the user needs to enable Trusted Platform Module (TPM) in the BIOS. The TPM is a specialized chip on the motherboard that stores information about the host system, such as encryption keys, digital certificates and passwords. When enabled, BitLocker can use the TPM chip.

**Boot Integrity:** Boot integrity ensures that the system can be trusted and has not been altered while the operating system loads. (UEFI recommended)

**Measured Boot:** provides stronger validation than Secure Boot. Measured Boot measures each component starting with the firmware through to the boot start drivers, and stores the measurements in the TMP chip to create a log. The log can be tested remotely to verify the boot state of the client. Measured Boot can identify untrusted applications trying to load, and it also allows antimalware to load earlier.

##  Physical Protection of Devices

Computer equipment to physically protect computer equipment:

* Use cable locks to secure devices
* Keep telecommunication rooms locked
* Use security cages (Faraday cages) around equipment * to block electromagnetic fields.
* Door locks

* **Radio frequency identification (RFID)** systems
RFID uses radio waves to identify and track objects. RFID tags can be attached to any item that an organization wants to track.


