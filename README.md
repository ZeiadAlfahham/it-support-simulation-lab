# IT Support Simulation Lab

A self-contained enterprise IT environment built to practice the full lifecycle of IT support and systems administration — from infrastructure design and Active Directory deployment to helpdesk operations using osTicket.

## Project Overview

This lab simulates a small enterprise environment consisting of:

- Windows Server 2022 Domain Controller
- Windows 10 domain-joined workstation
- Docker-based osTicket helpdesk system

The goal was to practice Active Directory administration, Group Policy management, permissions, troubleshooting, and real-world IT support workflows.

## Lab Architecture

### DC01 - Windows Server 2022

Configured with:

- Active Directory Domain Services
- DNS
- Domain: `corp.local`
- Organizational Units
- Security Groups
- Group Policy Objects
- NTFS permissions

### CLIENT01 - Windows 10

Configured with:

- Domain membership
- User testing
- GPO verification
- Network drive validation

### Helpdesk System

Deployed using Docker Compose:

- osTicket
- MySQL 5.7

Used to simulate a real IT ticket lifecycle.

## Active Directory Configuration

Implemented:

- HR, Sales, IT-Support, Disabled-Accounts OUs
- Security groups:
  - HR-Team
  - Sales-Team
  - IT-Admins
  - Sales-HR-Project-Team

Configured:

- NTFS permissions
- Group Policy drive mapping
- Item-level targeting
- Account lockout policy

## IT Support Scenarios

Completed four realistic support tickets:

### 1. Account Lockout

- User locked after failed login attempts
- Account unlocked through ADUC
- Login verified successfully

### 2. New-Hire Onboarding

- Created new user account
- Assigned department group membership
- Forced password change at first login

### 3. Cross-Department Permissions

- Created scoped security group
- Applied least-privilege access
- Verified correct resource access

### 4. Employee Offboarding

- Disabled user account
- Moved account to Disabled-Accounts OU

## Technologies

- Windows Server 2022
- Windows 10
- Active Directory
- DNS
- Group Policy
- NTFS Permissions
- Docker Compose
- MySQL
- osTicket
- Oracle VirtualBox

## Documentation

Full technical report:

`IT_Support_Simulation_Lab_Report.docx`

Screenshots:

`screenshots/`
