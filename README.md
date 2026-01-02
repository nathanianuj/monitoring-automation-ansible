# Automation with Ansible (SNMPv3)

This project automates the installation and configuration of **Prometheus SNMP Exporter**
using **Ansible**, with support for **SNMPv3** and a **resilient generator + fallback design**.

## 🚀 Features
- Installs SNMP Exporter from official releases
- Supports SNMPv3 (authPriv)
- Uses SNMP exporter generator (best-effort)
- Falls back to a static `snmp.yml` if generator fails due to vendor MIB issues
- Systemd service setup
- SSH bootstrap for fresh containers/VMs
- Clean separation of logic, templates, and secrets
- Ready for Prometheus integration

## 📁 Project Structure
```text
inventory/
  ├── hosts.ini
  └── group_vars/
      └── snmp_exporter.yml
playbooks/
  └── snmp_exporter.yml
templates/
  ├── generator.yml.j2
  ├── snmp.yml.j2
  ├── snmp_exporter.service.j2
  └── snmp_exporter.default.j2
