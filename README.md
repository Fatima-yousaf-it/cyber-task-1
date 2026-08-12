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



### Step 3: Configure NAT Network

A custom NAT Network was created in VirtualBox using the:

```text
10.0.0.0/24
```

network.

### Step 4: Install Kali Linux

The Kali Linux virtual machine was downloaded and imported into VirtualBox.

### Step 5: Configure Kali Linux Networking

Kali Linux was configured to communicate with the other virtual machines through the custom NAT Network.

### Step 6: Create VM Snapshot

A snapshot of the configured Kali Linux VM was created to provide a restore point before performing security experiments.

The official lab workflow lists these six tasks as Phase 1.

## Phase 2 – Target Machines Setup

The second phase involved setting up additional virtual machines that can be used as targets for cybersecurity and penetration-testing exercises.

The configured environment included:

* Windows VM
* Additional Windows versions where required
* Android VM (optional)

After configuring the machines, connectivity was tested between the virtual machines using ping tests.

Snapshots were also created for the configured machines so that the environment could be restored after experiments.

The lab guide specifies installing Windows/Android virtual machines, performing connectivity tests between machines, and taking snapshots.

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
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
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

## Connectivity Testing

Connectivity between the virtual machines was tested using ICMP ping.

Example:

```bash
ping 10.0.0.X
```

Successful responses confirm that the virtual machines can communicate over the configured virtual network.

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
Interested in Cybersecurity, Ethical Hacking, Networking, and SEO

---

### References

Lab setup based on the provided **Practical Lab Environment Setup for Pentesting, Ethical Hacking & Cybersecurity** guide by NetworkWalks Academy.

