# 📌 Azure Windows Server DHCP Multi-Scope Lab
## 📖 Project Overview

This lab demonstrates hands-on experience configuring a Windows Server DHCP service in Microsoft Azure, simulating how DHCP is deployed and managed in a real corporate network environment.

The focus is on server-side DHCP administration, including:

Installing the DHCP Server role

Creating and managing multiple scopes

Configuring exclusions and lease durations

Setting DHCP options (Gateway, DNS, Domain)

Creating reservations

Validating configuration without client testing

Due to Azure’s platform-managed networking, the lab emphasizes administrative configuration and validation rather than live client lease testing.

## 🎯 Objectives

The goal of this project was to practice enterprise-style DHCP configuration by:

Designing multiple DHCP scopes for different network types

Protecting infrastructure IPs with exclusions

Assigning appropriate lease durations

Configuring essential DHCP options

Creating device reservations

Verifying configuration through server tools

## 🛠️ Technologies Used

Microsoft Azure

Windows Server (latest)

DHCP Server Role

RDP

Azure Virtual Networking

## 🧱 Lab Architecture

Resource Group: rg-dhcp-lab

Virtual Network: vnet-dhcp-lab

Subnet: Default

Server VM: dc1 (Windows Server)

Access: RDP (restricted to my IP)

The Windows Server VM hosts the DHCP service and simulates an on-prem DHCP server.

## 📡 DHCP Scopes Configured
###1. Users LAN

Range: 192.168.1.10 – 192.168.1.200

Exclusions: 192.168.1.10 – 192.168.1.20

Lease: 8 hours

Purpose: User devices

###2. Corporate Voice (VoIP)

Range: 192.168.2.10 – 192.168.2.150

Exclusions: 192.168.2.10 – 192.168.2.30

Lease: 1 day

Purpose: Voice systems and gateways

###3. Guest Wi-Fi

Range: 192.168.3.50 – 192.168.3.250

Exclusions: 192.168.3.50 – 192.168.3.60

Lease: 2 hours

Purpose: Guest and transient devices

⚙️ DHCP Options Configured

Each scope was configured with:

003 Router: 192.168.X.254

006 DNS Server: IP of dc1

015 DNS Domain: lab.local

These settings reflect real-world enterprise DHCP standards.

🖨️ DHCP Reservation Example

A reservation was created for a network printer:

Name: Printer-01

IP: 192.168.1.15

MAC: Placeholder value

Scope: Users LAN

This demonstrates how to maintain consistent IPs without static assignments.

## ✅ Configuration Validation

The DHCP setup was verified using server-side checks:

All scopes show Active

Exclusions fall inside scope ranges

DHCP options reflect correct values

Reservations appear under correct scopes

DHCP service is running without errors

This mirrors real-world hybrid and on-prem DHCP administration tasks.

## 📚 What I Learned

This lab reinforced:

Enterprise DHCP design

Multi-scope management

Option configuration

Lease strategy

Reservation use cases

Server-side validation

Azure vs on-prem networking differences

🏁 Completion Checklist

✔ All scopes created and active
✔ Exclusions configured correctly
✔ DHCP options set per scope
✔ Logical lease durations applied
✔ Reservation created
✔ DHCP service running
