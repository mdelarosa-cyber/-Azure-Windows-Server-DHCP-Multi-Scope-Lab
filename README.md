# 📌 Azure Windows Server DHCP Multi-Scope Lab
## 📖 Project Overview

This project demonstrates hands-on experience configuring a Windows Server DHCP service in a simulated enterprise environment using Microsoft Azure. The lab focused on multi-scope DHCP configuration, exclusions, lease management, and reservations to reflect real-world network administration practices.

I built the environment from scratch in Azure, deployed a Windows Server VM, installed the DHCP role, and configured multiple scopes representing different network segments such as users, voice systems, and guest Wi-Fi.

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

Windows Server (2025)

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

## 📡 DHCP Configuration Summary

I configured the DHCP service to support multiple simulated network segments:

Users LAN

Created a scope for standard user devices

Defined an IP range for client systems

Added exclusions for infrastructure devices

Set an 8-hour lease duration

Corporate Voice (VoIP)

Built a separate scope for voice systems

Reserved IP ranges for gateways and call managers

Applied a longer 1-day lease

Guest Wi-Fi

Created a scope for guest devices

Used short lease times (2 hours) for high device turnover

Protected wireless controller IPs with exclusions

Each scope was activated and verified through the DHCP console.

## ⚙️ DHCP Options Configuration

For every scope, I configured:

Default Gateway (003 Router) to simulate edge devices

DNS Server (006) pointing to the Windows Server

DNS Domain (015) for naming consistency

These options reflect common enterprise DHCP configurations.

## 🖨️ DHCP Reservations

To demonstrate consistent device addressing without static IPs, I:

Created a reservation for a simulated printer

Assigned a fixed IP tied to a MAC address

Placed the reservation under the correct scope

This mirrors how shared devices are managed in corporate networks.

## ✅ Configuration Validation

Since Azure does not allow Windows Server VMs to issue DHCP leases, I validated the setup using server-side checks:

Confirmed all scopes were active

Verified exclusions were inside scope ranges

Ensured DHCP options were correctly applied

Confirmed reservations appeared correctly

Checked that the DHCP service was running

This reflects how administrators verify DHCP in real environments.

## ☁️ Azure Networking Limitation

Azure assigns IP addresses using its own platform-managed DHCP service.
Because of this, a Windows Server VM cannot act as the authoritative DHCP server for Azure subnets.

This lab focused on configuration and administration, which still directly maps to real-world on-prem and hybrid network management.

##  Key Takeaways

Through this lab, I learned:

How to design multi-scope DHCP environments

Why exclusions must fall within scope ranges

How lease duration impacts different device types

When to use reservations instead of static IPs

How to validate DHCP without live clients

## 📚 Skills Demonstrated

This project demonstrates practical skills in:

Windows Server Administration

DHCP & IP Address Management

Azure Infrastructure

Network Services Configuration

Troubleshooting & Validation

Enterprise Network Design

## 🧠 Reflection

If this were deployed in an on-prem environment, client devices would receive leases directly from the Windows Server DHCP service. Future enhancements could include:

Adding Active Directory integration

Testing real DHCP leases with client VMs

Implementing failover DHCP servers

Expanding subnet designs

🏁 Completion Checklist

✔ Windows Server deployed
✔ DHCP role installed
✔ Multiple scopes created
✔ Exclusions configured
✔ Options applied
✔ Reservation created
✔ Service validated
