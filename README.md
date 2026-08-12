# Cybersecurity & Ethical Hacking Lab Environment

## Overview

This repository documents my hands-on setup of a practical Cybersecurity, Ethical Hacking, and Penetration Testing Lab Environment using virtual machines and VirtualBox.

The lab was created as an isolated environment for practicing cybersecurity concepts, network configuration, ethical hacking techniques, penetration testing, and future CTF-based exercises.

The setup follows a two-phase approach covering the installation and configuration of VirtualBox, Kali Linux, Windows virtual machines, network configuration, IP addressing, connectivity testing, and VM snapshots.

## Lab Objectives

* Build an isolated cybersecurity practice environment
* Configure VirtualBox networking using a custom NAT Network
* Install and configure Kali Linux
* Configure Windows virtual machines for security testing
* Assign and verify IP configurations
* Test connectivity between virtual machines
* Create VM snapshots for safe experimentation and rollback
* Prepare the environment for future CTF and penetration-testing labs

## Lab Environment

### Virtualization

* VirtualBox
* 7-Zip
* Multiple Virtual Machines

### Operating Systems

* Kali Linux
* Windows 10/11/7
* Android VM (optional)

### Network

* Network Type: NAT Network
* Network Range: `10.0.0.0/24`
* Configured IP range: `10.0.0.2 - 10.0.0.99`

The lab guide specifies a custom NAT Network for the virtual machines and provides example manual IP addresses within the `10.0.0.0/24` network.

## Phase 1 – Kali Linux Setup

### Step 1: Install 7-Zip

7-Zip was installed to extract and manage downloaded virtual machine files.

### Step 2: Install VirtualBox

Oracle VirtualBox was installed as the virtualization platform for creating and managing the cybersecurity lab machines.
<img width="1913" height="462" alt="image" src="https://github.com/user-attachments/assets/da407512-9293-4318-b1e9-70716cebe20a" />



### Step 3: Configure NAT Network

A custom NAT Network was created in VirtualBox using the:

```text
10.0.0.0/24
```

network.
<img width="1278" height="677" alt="image" src="https://github.com/user-attachments/assets/f0dea710-cff7-43ba-af69-505fc3141fbb" />


### Step 4: Install Kali Linux

The Kali Linux virtual machine was downloaded and imported into VirtualBox.

### Step 5: Configure Kali Linux Networking

Kali Linux was configured to communicate with the other virtual machines through the custom NAT Network.
<img width="765" height="695" alt="image" src="https://github.com/user-attachments/assets/1d158be0-a2cd-42ff-b0d9-14b0c3c4aee9" />

<img width="839" height="504" alt="image" src="https://github.com/user-attachments/assets/71b89bba-408f-4a73-8e00-ae011433dc3a" />


### Step 6: Create VM Snapshot

A snapshot of the configured Kali Linux VM was created to provide a restore point before performing security experiments.

The official lab workflow lists these six tasks as Phase 1.

## Network Topology

The general lab architecture can be represented as:

```text
                 Host Machine
                     |
               VirtualBox
                     |
              NAT Network
             10.0.0.0/24
                     |
       +-------------+-------------+
       |             |             |
     Kali         Windows       Android
   Linux VM         VM            VM
       |             |             |
       +-------------+-------------+
              Connectivity Tests
```

## Example IP Configuration

The lab uses the `10.0.0.0/24` network. Example addresses from the lab setup include:

| Machine    | Example IP  |
| ---------- | ----------- |
| Kali Linux | `10.0.0.2`  |
| VM 2       | `10.0.0.10` |
| VM 3       | `10.0.0.7`  |
| VM 4       | `10.0.0.16` |
| VM 5       | `10.0.0.9`  |
| VM 6       | `10.0.0.11` |

These addresses are examples from the lab guide; the actual addresses used in my implementation may differ depending on my VirtualBox configuration.

## Kali Linux Connectivity Troubleshooting

During the setup, the lab documentation provides a troubleshooting command for Internet connectivity issues with Kali Linux 2026.1 or later:

```bash
sudo nmcli connection modify "eth0" ipv4.dad-timeout 0
```

The guide also notes using `10.0.0.1` in certain situations if Internet connectivity causes issues.

## Virtual Machine Snapshots

Snapshots were created after configuring the virtual machines.

Snapshots are useful in a cybersecurity lab because they allow the environment to be restored to a known working state after performing potentially disruptive experiments.

Recommended snapshot points include:

* Fresh OS installation
* Network configuration completed
* Kali Linux configured
* Target machine configured
* Pre-exploitation state

<img width="1234" height="570" alt="image" src="https://github.com/user-attachments/assets/a36c7557-a554-4489-bb22-1a833fb056cf" />

## Connectivity Testing

Connectivity between the virtual machines was tested using ICMP ping.

Example:

```bash
ping 10.0.0.X
```

Successful responses confirm that the virtual machines can communicate over the configured virtual network.
<img width="1693" height="987" alt="image" src="https://github.com/user-attachments/assets/4da7dfd7-a181-4e02-a63a-4f3042ec98af" />




## Skills Demonstrated

This project demonstrates practical experience with:

* VirtualBox
* Virtual machine deployment
* Kali Linux
* Windows virtual machines
* NAT Network configuration
* IPv4 addressing
* Basic network troubleshooting
* VM snapshots
* Virtualized cybersecurity environments
* Network connectivity testing
* Cybersecurity lab preparation
* Ethical hacking environment setup

## Future Labs

This environment can be extended for practical cybersecurity exercises such as:

* Network reconnaissance
* Vulnerability assessment
* Web application security testing
* Network security testing
* Exploitation in controlled environments
* Digital forensics exercises
* Capture The Flag (CTF) challenges
* Security monitoring and analysis

The lab documentation also notes that additional offline virtual machines may be used for future CTF practical labs and challenges.

## Disclaimer

This repository is intended for **educational and authorized cybersecurity testing only**.

All security testing should be performed only against systems and networks that you own or have explicit permission to test.

## Project Status

**Completed**

The virtual cybersecurity lab environment has been configured and tested according to the provided lab requirements.

---

### Author

**Fatima Yousaf**

Cybersecurity & IT Student
Cybersecurity B082 
Interested in Cybersecurity, Ethical Hacking, Networking

---

### References

Lab setup based on the provided **Practical Lab Environment Setup for Pentesting, Ethical Hacking & Cybersecurity** guide by NetworkWalks Academy.

