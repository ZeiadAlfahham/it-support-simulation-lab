# IT Support Simulation Lab


A complete enterprise IT support and system administration simulation environment built to replicate real-world business infrastructure, user management, security policies, troubleshooting workflows, and helpdesk operations.

The project demonstrates the full IT support lifecycle:

- Infrastructure deployment
- Active Directory administration
- User and group management
- Group Policy implementation
- Access control configuration
- Troubleshooting real support incidents
- Helpdesk ticket management using osTicket

---

# Table of Contents

- [Lab Architecture](#lab-architecture)
- [Active Directory Implementation](#active-directory-implementation)
- [IT Support Scenarios](#it-support-scenarios)
- [Ticketing System Deployment](#ticketing-system-deployment)
- [Project Screenshots](#project-screenshots)
- [Documentation](#documentation)
- [Technologies Used](#technologies-used)
- [Skills Demonstrated](#skills-demonstrated)
- [Project Goal](#project-goal)

---

# Lab Architecture

The environment consists of two Windows virtual machines running on an isolated Oracle VirtualBox NAT network.

## Network Design

```
                Enterprise Lab Network

                       NAT Network

                           |
                           |
              +------------+------------+
              |                         |
          DC01 Server              CLIENT01
       Windows Server 2022       Windows 10
              |                         |
              |
     Active Directory Domain
          corp.local
```

---

# DC01 — Windows Server 2022

Configured as the enterprise Domain Controller.

Implemented services:

- Active Directory Domain Services (AD DS)
- DNS Server
- Domain Controller
- Organizational Units
- Security Groups
- Group Policy Objects
- NTFS Permissions


Resources:

| Resource | Configuration |
|---|---|
| RAM | 4096 MB |
| CPU | 2 Processors |
| Storage | 60 GB |

---

# CLIENT01 — Windows 10

Domain-joined workstation used for:

- User authentication testing
- Group Policy verification
- Network drive validation
- Permission testing
- Support scenario simulation


Resources:

| Resource | Configuration |
|---|---|
| RAM | 4096 MB |
| CPU | 2 Processors |
| Storage | 40 GB |

---

# Active Directory Implementation

## Organizational Units

Created enterprise-style organizational structure:

```
corp.local
│
├── HR
├── Sales
├── IT-Support
└── Disabled-Accounts
```

---

## Security Groups

Implemented role-based access control using:

- HR-Team
- Sales-Team
- IT-Admins
- Sales-HR-Project-Team

---

# Group Policy Configuration

## Sales Drive Mapping

Created Group Policy Object:

```
Sales - Map Drive
```

Implemented:

- Automatic S: network drive mapping
- OU-based deployment
- Security group filtering
- Item-level targeting


---

## Account Lockout Policy

Configured security policy:

- Maximum failed attempts: 5
- Lockout duration: 30 minutes
- Reset counter period: 30 minutes

---

# IT Support Scenarios

Four realistic enterprise support cases were simulated from ticket creation to resolution.

---

# Scenario 1 — Account Lockout

## Problem

A user was unable to authenticate after multiple incorrect password attempts.

## Resolution

- Located locked account in Active Directory Users and Computers
- Unlocked user account
- Verified successful authentication

---

# Scenario 2 — New Employee Onboarding

## Problem

A new employee required access to company resources.

## Resolution

- Created Active Directory user account
- Assigned department membership
- Configured first-login password change
- Verified successful login

---

# Scenario 3 — Cross Department Permissions

## Problem

An HR employee required controlled access to a shared Sales project folder.

## Resolution

- Created dedicated security group
- Applied least-privilege NTFS permissions
- Verified authorized and unauthorized access

---

# Scenario 4 — Employee Offboarding

## Problem

A terminated employee required immediate access removal.

## Resolution

- Disabled user account
- Moved account into Disabled-Accounts OU
- Verified login prevention
- Preserved account records

---

# Ticketing System Deployment

A complete helpdesk environment was deployed using Docker Compose.

## Components

- osTicket
- MySQL 5.7
- Docker


Implemented:

- IT Support department
- Agent accounts
- User ticket submission
- Ticket assignment
- Resolution workflow


All Active Directory incidents were documented as real IT support tickets.

---

# Project Screenshots

The screenshots below provide evidence of:

- Virtual machine deployment
- Active Directory configuration
- Group Policy implementation
- Security permissions
- Support scenarios
- Helpdesk operations


## Virtual Machine Setup

### DC01 — Domain Controller

![DC01](screenshots/01-vm-setup/Figure%201.1%20-%20DC01%20VirtualBox%20Details.png)


### CLIENT01 — Workstation

![CLIENT01](screenshots/01-vm-setup/Figure%201.2%20-%20CLIENT01%20VirtualBox%20Details.png)


---

# Active Directory Structure

### Organizational Units

![OU Structure](screenshots/03-ad-structure/Figure%204.1%20-%20OU%20Tree%20in%20ADUC.png)


---

# Group Policy

### Drive Mapping

![Drive Mapping](screenshots/03-ad-structure/Figure%204.3%20-%20GPO%20Drive%20Maps%20Configuration.png)


### Account Lockout Policy

![Lockout Policy](screenshots/03-ad-structure/Figure%204.5%20-%20Account%20Lockout%20Policy%20Settings.png)


---

# Scenario Evidence

## Account Lockout Resolution

![Account Unlock](screenshots/05-scenario-1-lockout/Figure%206.1.5%20-%20Scenario1%20Unlock%20Account%20Checkbox.png)


## Employee Onboarding

![New User](screenshots/06-scenario-2-onboarding/Figure%206.2.2%20-%20Scenario2%20Initial%20Password%20Setup.png)


## Permission Management

![NTFS Permissions](screenshots/07-scenario-3-permissions/Figure%204.2%20-%20NTFS%20Permissions%20on%20Sales%20Folder.png)


## Employee Offboarding

![Offboarding](screenshots/08-scenario-4-offboarding/Figure%206.4.2%20-%20Scenario4%20Moving%20to%20Disabled-Accounts%20OU.png)


---

# Helpdesk Ticketing System

Additional evidence:

```
screenshots/09-osticket-deployment/
screenshots/10-resolved-tickets/
```

Includes:

- Ticket creation
- User requests
- Agent responses
- Resolution documentation

---

# Documentation

Complete technical report:

```
IT_Support_Simulation_Lab_Report.docx
```

Includes:

- Full implementation steps
- 50+ pages of documentation
- 70+ verification screenshots
- Troubleshooting analysis
- Root cause explanations

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

- Windows Server Administration
- Active Directory Management
- User and Group Administration
- Group Policy Configuration
- Access Control Management
- Least Privilege Implementation
- IT Troubleshooting
- Helpdesk Operations
- Ticket Management
- Docker Deployment
- Technical Documentation

---

# Project Goal

This project was created to simulate real enterprise IT support responsibilities by combining:

- Infrastructure administration
- Identity and access management
- Security best practices
- User support workflows
- Troubleshooting methodologies
- Professional technical documentation

The goal was to build practical experience similar to the responsibilities of an **IT Support Specialist, System Administrator, or Junior Security Analyst**.
