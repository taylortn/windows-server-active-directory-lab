# Windows Server Active Directory Lab

## Overview
This project documents my hands-on experience building a Windows Server environment using Oracle VirtualBox. The goal is to develop real-world system administration skills, including Active Directory configuration and management.

## Lab Environment
- Hypervisor: Oracle VirtualBox
- OS: Windows Server Evaluation
- VM Name: WS2025-DC01
- RAM: 4096 MB
- CPU: 2
- Disk: 50 GB
- Network: NAT

## Progress
- [x] Created Virtual Machine
- [x] Installed Windows Server
- [ ] Rename server
- [ ] Configure static IP
- [ ] Install Active Directory
- [ ] Create users and groups
- [ ] Apply Group Policy

## Issue Encountered
Received error: "There is an error selecting this partition for install."

## Root Cause
The virtual disk partition was not properly initialized or formatted.

## Resolution
Deleted the existing partition and allowed Windows Server installer to automatically create and format partitions using unallocated space.

## Lesson Learned
Proper disk initialization and partitioning are required before OS installation. When errors occur, removing existing partitions and starting with unallocated space can resolve installation issues.

## Issue Encountered - Installation Failure

## Problem
Windows Server installation failed, and the system displayed:
"An operating system wasn't found."

## Root Cause
Initial VM setup included unattended installation and improper disk initialization, leading to a corrupted install state.

## Resolution
- Deleted the VM entirely
- Recreated VM with manual installation only
- Disabled unattended installation
- Allowed Windows to handle partitioning automatically

## Lesson Learned
When OS installation fails in a VM, rebuilding a clean one is often faster and more reliable than troubleshooting a corrupted setup. Also, avoid automated/unattended installs when learning core system setup.

## Issue Encountered - Installed Server Core Instead of Desktop Experience

## Problem
Installed Windows Server without "Desktop Experience," resulting in a command-line-only interface (Server Core).

## Root Cause
Incorrect selection during installation phase.

## Resolution
Reinstalled Windows Server and selected "Standard Evaluation (Desktop Experience)" to enable graphical user interface.

## Lesson Learned
Windows Server installation includes multiple modes. "Server Core" is minimal and command-line-based, while "Desktop Experience" provides a GUI. Proper selection is critical depending on use case.

## Windows Server Installation Completed

## Summary
Successfully installed Windows Server 2025 Standard Evaluation (Desktop Experience) on a virtual machine using Oracle VirtualBox.

## Configuration
- Administrator account configured
- GUI-based environment enabled (Desktop Experience)

## Outcome
Server is now accessible via desktop interface and ready for further configuration such as renaming, networking, and Active Directory setup.

## Server Configuration

### Server Name Change
- Renamed server from WS2025-DC01 to LAB-DC01
- Restarted system to apply changes

### Network Configuration
- Assigned static IP address
- Configured DNS to point to local server
- Prepared environment for Active Directory installation

### Importance
Static IP and proper naming are critical for domain controller functionality and network stability.

## Network Adapter Configuration

Attempted to rename network adapter while interface was still in "Identifying" state. Learned that network initialization can delay certain GUI actions. Continued with configuration and used alternative methods when needed.

## Active Directory Installation

### Role Installed
- Active Directory Domain Services (AD DS)

### Domain Configuration
- Created new forest
- Domain name: lab.local

### Domain Controller Promotion
- Server promoted to Domain Controller
- Configured Directory Services Restore Mode (DSRM)

### Outcome
Server is now functioning as a Domain Controller and managing directory services for the lab environment.

## Domain Controller Promotion

### Actions Completed
- Promoted server to Domain Controller
- Created new forest: lab.local
- Configured Directory Services Restore Mode (DSRM)

### Services Enabled
- Active Directory Domain Services
- DNS Server

### Outcome
Server is now functioning as a Domain Controller, providing centralized authentication and directory services.

## Issue Encountered - Password Policy Enforcement

### Problem
Unable to create user due to password not meeting Active Directory complexity requirements.

### Root Cause
Domain-level password policy enforces:
- Minimum length
- Complexity (uppercase, lowercase, number, special character)

### Resolution
Updated password to meet complexity requirements and successfully created user.

### Lesson Learned
Active Directory enforces security policies by default, ensuring strong authentication practices across the domain.

## Issue Encountered - UEFI Boot Failure

### Problem
Client VM failed to boot from ISO and entered UEFI Boot Manager.

### Root Cause
UEFI boot mode caused issues with recognizing the bootable ISO.

### Resolution
Disabled EFI in VirtualBox settings and prioritized optical drive in boot order.

### Lesson Learned
Boot mode (UEFI vs BIOS) can affect virtual machine behavior and ISO boot compatibility.

## Issue Encountered - Secure Boot Blocking Installation

### Problem
VM failed to boot from Windows ISO while Secure Boot and UEFI were enabled.

### Root Cause
Secure Boot prevented unsigned or incompatible boot media from loading in VirtualBox environment.

### Resolution
Disabled Secure Boot and switched to BIOS boot mode for compatibility.

### Lesson Learned
Secure Boot and UEFI can interfere with virtual machine installations, especially in lab environments.
