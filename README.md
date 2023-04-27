# Linux-DNS-Configuration
⚙This repository contains 4 configuration files for setting up DNS on a Linux system.

The configuration files are named as follows:

-   `dhcpd.conf`: DHCP configuration file for setting up leases and assigning IP addresses to clients.
-   `named.conf.local`: Local DNS configuration file for resolving local domain names.
-   `named.conf.options`: Global DNS configuration file for setting options and default values for the DNS server.
-   `zone.gsx`: Zone file containing DNS records for the `intranet.gsx` domain.

### Prerequisites

-   A Linux system with `dhcpd` and `bind9` installed.
-   Root privileges to modify system configuration files.

### DHCP Configuration (dhcpd.conf)

The `dhcpd.conf` file contains configuration for DHCP leases and IP address assignments for clients. Sample configurations are provided in the file, and you can modify them according to your network requirements.

### Local DNS Configuration (named.conf.local)

The `named.conf.local` file contains local DNS configuration for resolving local domain names. This file should be edited to add zones and their associated files.

### Global DNS Configuration (named.conf.options)

The `named.conf.options` file contains global DNS configuration options and default values for the DNS server. This file should be edited to set global DNS settings such as forwarding and logging.

### Zone Configuration (zone.gsx)

The `zone.gsx` file contains DNS records for the `intranet.gsx` domain. The file contains configuration for `SOA`, `NS`, `A`, `MX`, and other record types. You can modify the file to add your own DNS records.

### Usage

1.  Copy the files to their respective locations:
    
    `sudo cp dhcpd.conf /etc/dhcp/dhcpd.conf
    sudo cp named.conf.local /etc/bind/named.conf.local
    sudo cp named.conf.options /etc/bind/named.conf.options
    sudo cp zone.gsx /etc/bind/zones/zone.gsx` 
    
2.  Restart the services:
    
    `sudo systemctl restart isc-dhcp-server
    sudo systemctl restart bind9` 
    

### Additional Notes

-   Make sure to modify the configuration files according to your network requirements.
-   Use `systemctl status` to check the status of the services and to troubleshoot any issues.
-   The `zone.gsx` file contains sample DNS records. Make sure to modify them according to your own domain requirements.
-   For more information on DHCP and DNS configuration, refer to the [official documentation](https://help.ubuntu.com/community/BIND9ServerHowto) for Ubuntu.
