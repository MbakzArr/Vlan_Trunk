# VLAN and IP Configuration README

The network setup involves configuring VLANs, assigning ports to VLANs, creating a trunk with a native VLAN, specifying allowed VLANs, and setting up IP addresses for various devices.

## Network Topology

The network consists of two switches, S1 and S2, along with four PCs (PC1, PC2, PC3, and PC4).

## VLAN Configuration

### VLAN 10

- Ports: S1VLAN, PC1Fa, PC3Fa
- Subnet: 10.129.10.0/24
- IPv4 Address Range: 10.129.10.11 - 10.129.10.12
- IPv6 Prefix: 2001:129:10::/64
- Unicast Addresses: 2001:129:10::11, 2001:129:10::12

### VLAN 20

- Ports: S1VLAN, PC2Fa, PC4Fa
- Subnet: 20.129.20.0/24
- IPv4 Address Range: 20.129.20.11 - 20.129.20.12
- IPv6 Prefix: 2001:129:20::/64
- Unicast Addresses: 2001:129:20::11, 2001:129:20::12

## Trunk Configuration

- Trunk Interface: S2 (Assuming a connection between S1 and S2)
- Native VLAN: VLAN 10 (Native VLAN carries untagged traffic)
- Allowed VLANs: VLAN 10 and VLAN 20

## IP Address Configuration

### S1

- Interface: S1VLAN
  - IPv4 Address: 10.129.10.11/24
  - IPv6 Address: 2001:129:10::11/64

### PC1

- Interface: PC1Fa
  - IPv4 Address: 10.129.10.1/24
  - IPv6 Address: 2001:129:10::1/64

### PC2

- Interface: PC2Fa
  - IPv4 Address: 20.129.20.2/24
  - IPv6 Address: 2001:129:20::2/64

### PC3

- Interface: PC3Fa
  - IPv4 Address: 10.129.10.3/24
  - IPv6 Address: 2001:129:10::3/64

### PC4

- Interface: PC4Fa
  - IPv4 Address: 20.129.20.4/24
  - IPv6 Address: 2001:129:20::4/64

## S2

- Since specific VLAN assignments and IP addresses for S2 were not provided, this section assumes S2 is involved in trunking and VLAN propagation as described above.

## Important Notes

- Verify that the configuration matches your intended network setup.
- Ensure that the devices are properly configured to support IPv6 if required.
- Double-check VLAN assignments and trunk configurations to prevent connectivity issues.


## Testing
• PC1 and PC3 can ping (IPv4 and IPv6) S1 and S2 VLAN 10 SVIs
• PC2 and PC4 can ping (IPv4 and IPv6) S1 and S2 VLAN 20 SVIs

• PC2 (IPv4 and IPv6) from PC1
• PC4 (IPv4 and IPv6) from PC2.
