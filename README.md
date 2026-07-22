# IT Support Simulation Lab

A self-contained enterprise IT environment built to practice the full lifecycle of IT support and systems administration — from infrastructure design and Active Directory deployment to helpdesk operations using a Docker-deployed ticketing system.

The project simulates a small enterprise environment where users, permissions, policies, troubleshooting scenarios, and support workflows are managed as they would be in a real IT environment.

---

# Lab Architecture

The environment consists of two virtual machines running on an isolated Oracle VirtualBox NAT network.

## DC01 — Windows Server 2022

Configured as the enterprise Domain Controller:

- Active Directory Domain Services (AD DS)
- DNS Server
- Domain: `corp.local`
- Organizational Units
- Security Groups
- Group Policy Objects
- NTFS Permissions

Resources:

- 4096 MB RAM
- 2 Processors
- 60 GB Storage


## CLIENT01 — Windows 10

Domain-joined workstation used for:

- User testing
- Group Policy verification
- Network drive validation
- Access control testing

Resources:

- 4096 MB RAM
- 2 Processors
- 40 GB Storage

---

# Active Directory Implementation

## Organizational Units

Created the following structure:

- HR
- Sales
- IT-Support
- Disabled-Accounts


## Security Groups

Implemented role-based access control using:

- HR-Team
- Sales-Team
- IT-Admins
- Sales-HR-Project-Team


## Group Policy Configuration

Implemented enterprise-style policies:

### Sales Drive Mapping

Created:

`Sales - Map Drive`

Features:

- Automatic S: network drive mapping
- Applied to Sales OU
- Security group filtering
- Item-level targeting


### Account Lockout Policy

Configured:

- 5 failed login attempts
- 30-minute account lockout duration
- 30-minute counter reset period

---

# IT Support Scenarios

Four realistic support scenarios were completed from issue identification to resolution.

## 1. Account Lockout

Scenario:

A user was unable to access their account after multiple failed login attempts.

Resolution:

- Identified locked account in Active Directory Users and Computers
- Unlocked the user account
- Verified successful login


## 2. New-Hire Onboarding

Scenario:

A new employee required access to company resources.

Resolution:

- Created new Active Directory account
- Assigned department group membership
- Forced password change at first login


## 3. Cross-Department Permissions

Scenario:

An HR employee required access to a shared Sales project folder.

Resolution:

- Created Sales-HR-Project-Team security group
- Applied least-privilege permissions
- Verified access restrictions


## 4. Employee Offboarding

Scenario:

A departed employee needed access removed.

Resolution:

- Disabled user account
- Moved account into Disabled-Accounts OU
- Preserved account records

---

# Ticketing System Deployment

A helpdesk environment was deployed using Docker Compose.

Components:

- osTicket
- MySQL 5.7

Implemented:

- Custom IT Support department
- Agent configuration
- User ticket submission
- Ticket resolution workflow

All Active Directory scenarios were documented as real support tickets.

---

# Project Screenshots

## Virtual Machine Setup

![VirtualBox Setup](screenshots/01-vm-setup/Figure%201.1%20-%20DC01%20VirtualBox%20Details.png)

![Client VM Setup](screenshots/01-vm-setup/Figure%201.2%20-%20CLIENT01%20VirtualBox%20Details.png)


## Domain Controller

![DC01 Login](screenshots/02-domain-controller/Figure%203.1%20-%20DC01%20Login%20Screen%20(CORP%20Administrator).png)

![Server Manager](screenshots/02-domain-controller/Figure%203.2%20-%20Server%20Manager%20Dashboard%20(AD%20DS%20and%20DNS).png)


More screenshots are available in:

`screenshots/`

---

# Documentation

Full technical documentation:

`IT_Support_Simulation_Lab_Report.docx`

The report includes:

- 50+ pages of documentation
- 70+ verification screenshots
- Troubleshooting table
- Root cause analysis


---

# Technologies Used

- Windows Server 2022
- Windows 10
- Active Directory Domain Services
- DNS
- Group Policy
- NTFS Permissions
- Docker Compose
- MySQL
- osTicket
- Oracle VirtualBox


---

# Skills Demonstrated

- Enterprise environment design
- Windows Server administration
- Active Directory management
- User and group administration
- Group Policy configuration
- Access control and permissions
- Least-privilege implementation
- IT troubleshooting
- Helpdesk ticket management
- Docker deployment


---

# Project Goal

This project was built to simulate real-world IT support and system administration responsibilities, combining infrastructure management, user support, security practices, and documentation.
