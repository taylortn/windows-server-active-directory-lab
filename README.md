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
Proper disk initialization and partitioning is required before OS installation. When errors occur, removing existing partitions and starting with unallocated space can resolve installation issues.
