# Home Lab Technical Report

## Security Monitoring, Network Engineering, and Infrastructure Development

### Author

Stacey Menley

---

## Executive Summary

This home lab serves as my personal cybersecurity engineering and network operations environment. It was designed to provide practical experience with enterprise networking concepts, Linux administration, log management, network monitoring, security analytics, infrastructure troubleshooting, and future SOC-focused projects.

The environment continues to evolve as I expand my skills in security operations, detection engineering, automation, network visibility, and infrastructure management. While this lab is a personal project, I approach it with the same mindset used in professional environments: documenting architecture, validating configurations, monitoring traffic, and continuously improving security controls.

The lab has become a platform for experimenting with real-world technologies including OpenWrt, Docker, ELK Stack, Linux administration, NetFlow/IPFIX telemetry, network segmentation, IoT monitoring, and infrastructure automation.

---

## Lab Objectives

The primary goals of this environment are:

- Develop practical cybersecurity and SOC analyst skills  
- Build experience with Linux administration  
- Create centralized visibility into network activity  
- Learn network telemetry and flow analysis  
- Practice log collection, parsing, enrichment, and visualization  
- Develop troubleshooting and incident investigation methodologies  
- Explore automation and infrastructure management  
- Prepare for future enterprise-scale projects  

---

## Infrastructure Overview

The lab follows a layered architecture consisting of:

- Internet Connectivity  
- Gateway and Routing Layer  
- Managed Switching Layer  
- Monitoring and Analytics Layer  
- Endpoint Systems  
- IoT Devices  
- Future Expansion Infrastructure  

The design prioritizes visibility, documentation, and scalability while avoiding unnecessary exposure of internal systems.

---

## Hardware Inventory

### Internet Edge

#### ARRIS SURFboard SB8200 DOCSIS 3.1 Cable Modem

The ARRIS SB8200 serves as the internet-facing modem for the environment.

Key Features:

- DOCSIS 3.1 technology  
- Multi-gigabit capable architecture  
- Supports download speeds up to 2 Gbps  
- Dual Ethernet interfaces  
- Stable connectivity for monitoring and analytics workloads  

---

## Gateway and Routing Layer

### OpenWrt One Wireless Router

The OpenWrt One functions as the primary gateway, routing platform, and wireless infrastructure controller.

Specifications:

- ARMv8 Architecture  
- MediaTek platform  
- OpenWrt 24.03  
- Linux Kernel 6.6.x  
- Gigabit Ethernet interfaces  
- DHCP and DHCPv6 support  
- Wireless access point capabilities  

Primary Responsibilities:

- Internet gateway  
- Network routing  
- Wireless network management  
- DHCP services  
- Traffic forwarding  
- Device connectivity management  

---

## Managed Switching Layer

### Netgear GS108Tv3 Smart Managed Pro Switch

The Netgear managed switch acts as the core aggregation point for wired devices.

Features:

- 8 Gigabit Ethernet ports  
- VLAN support  
- Port mirroring capabilities  
- Traffic monitoring and segmentation  

---

## Monitoring and Analytics Platform

### Raspberry Pi 5 Analytics Node

Specifications:

- Quad-Core Cortex-A76 Processor  
- 8 GB RAM  
- Gigabit Ethernet  
- USB 3.0  

---

## ELK Stack Environment

### Elasticsearch

Stores and indexes telemetry and log data.

### Logstash

Processes and transforms incoming data streams.

### Kibana

Provides dashboards, visualizations, and investigation tools.

---

## Endpoint Systems

### Dell Latitude 5510

Primary engineering workstation used for:

- Documentation  
- Security investigations  
- GitHub management  
- Research and development  

---

## IoT Infrastructure

### AXIS M1075-L Network Camera

Used for IoT telemetry analysis and network visibility experimentation.

---

## Current Project: HELM

HELM focuses on improving network telemetry collection and SOC-style visibility using:

- NetFlow and IPFIX  
- Log pipelines  
- Dockerized services  
- ELK Stack analytics  
- Network traffic analysis  

---

## Skills Demonstrated

- Security Operations  
- Network Monitoring  
- Detection Engineering  
- Linux Administration  
- Docker Administration  
- Log Analysis  
- Infrastructure Documentation  
- ELK Stack Management  
- IoT Monitoring  
- Network Visibility Engineering  

---

## Planned Improvements

### Honeypot Environment

Planned research areas include:

- Threat intelligence collection  
- Adversary behavior analysis  
- Detection validation  
- Alert testing  

### Future Platforms

- Splunk Enterprise  
- Proxmox Virtualization  
- TrueNAS Storage  
- Ubuntu Server Expansion  
- VPN Infrastructure  
- Infrastructure Automation  

---

## Lessons Learned

Effective security monitoring begins with visibility. Building telemetry pipelines, troubleshooting infrastructure, and validating data flows require a systems-level understanding of how each component interacts within the environment.

This lab continues to evolve as a practical environment for developing real-world cybersecurity engineering and SOC analyst skills.
