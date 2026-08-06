# Ephemeral-Gateway

> 🚧 **WORK IN PROGRESS** 🚧
> 
> This script is actively under development. While it is fully functional and usable in its current state, please read the **Known Limitations** section carefully before running it on a production or daily-driver machine.

A lightweight utility script that instantly provisions a temporary network gateway using `iptables` for traffic forwarding, alongside a small DHCP and DNS server setup. It is designed to quickly deploy temporary, isolated networking environments.

## ⚠️ Known Limitations & Warnings

Because this project is currently a work in progress, there are a few important caveats to be aware of:

* **It leaves traces:** The script does not yet have a complete cleanup or teardown function. Once you stop the script, some temporary files, network interfaces, or routing rules may remain active on your system and require manual removal.
* **It alters system configurations:** This script modifies existing network configurations to function. **If you already use the same dependencies** (like running your own local DNS, DHCP server, or custom `iptables` rules), this script will likely overwrite or alter those configurations while running, which could disrupt your existing network setup.

**Recommendation:** It is highly recommended to run this script within a virtual machine, a disposable test environment, or a dedicated piece of hardware until the teardown and configuration isolation features are finalized.

## Prerequisites
* Linux environment
* Root/sudo privileges (required for network and iptables modification)
* Dependencies (Automatically installed if needed) dnsmasq, iptables, ip, sed.

## Usage

```bash
# Usage with all the default parameters.
sudo ./ephemeral-gateway
