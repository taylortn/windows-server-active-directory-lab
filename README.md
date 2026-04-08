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
