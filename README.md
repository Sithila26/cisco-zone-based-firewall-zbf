# Cisco Zone-Based Firewall (ZBF) Implementation with RIP Version 2

## Project Overview

This project demonstrates the implementation of a Cisco Zone-Based Firewall (ZBF) in Cisco Packet Tracer. The goal of the project is to secure communication between internal networks and server resources by applying firewall policies while maintaining connectivity through dynamic routing.

The network uses RIP Version 2 (RIPv2) to dynamically exchange routing information between routers. A Zone-Based Firewall is configured to inspect and control traffic flowing between the INSIDE and OUTSIDE security zones.

This project was created as a practical exercise to strengthen knowledge in routing, network security, firewall policies, and Cisco IOS configuration.

---

## Technologies Used

* Cisco Packet Tracer
* Cisco IOS
* Zone-Based Firewall (ZBF)
* RIP Version 2 (RIPv2)
* Access Control Lists (ACLs)
* Security Zones
* Zone Pair Policies
* Traffic Inspection

---

## Network Topology

![alt text](<Screenshot 2026-06-15 233615.png>)

---

## Project Objectives

The main objectives of this project were:

* Configure dynamic routing using RIP Version 2.
* Implement a Cisco Zone-Based Firewall.
* Create INSIDE and OUTSIDE security zones.
* Configure zone-pair policies for traffic inspection.
* Allow authorized traffic to reach server resources.
* Block unauthorized traffic according to security policies.
* Verify firewall functionality through practical testing.

---

## Network Structure

### Internal Network 1

Network: 10.10.10.0/24

Connected through Router R-01.

### Internal Network 2

Network: 10.10.11.0/24

Connected through Router R-01.

### Server Network

Network: 10.10.12.0/24

Connected through Router R-02.

### Firewall Segment

The Zone-Based Firewall is positioned between R-01 and R-02 and controls traffic moving between the internal networks and server resources.

---

## Routing Configuration

RIP Version 2 was configured on all routing devices to provide dynamic route exchange.

Key configuration features:

* RIP Version 2 enabled
* Automatic route learning
* No auto-summary enabled
* Route propagation between all connected networks

Verification Commands:

```bash
show ip protocols
show ip route
show ip rip database
```

---

## Zone-Based Firewall Configuration

The firewall was configured using Cisco Zone-Based Firewall architecture.

### Security Zones

INSIDE Zone

* Represents trusted internal networks.

OUTSIDE Zone

* Represents external/server-side networks.

### Zone Pair

A zone pair was created to allow controlled communication between the INSIDE and OUTSIDE zones.

### Traffic Inspection

Traffic inspection policies were applied using:

* Class Maps
* Policy Maps
* Zone Pairs

This allows the firewall to inspect and track permitted traffic sessions.

---

## Validation Tests

Several tests were performed to verify both connectivity and security policy enforcement.

### Authorized Traffic

PC-A (10.10.10.10)

```bash
ping 10.10.12.10
```

Result:

Successful

PC-C (10.10.11.10)

```bash
ping 10.10.12.10
```

Result:

Successful

These results confirm that authorized hosts are able to communicate with the server network.

---

### Unauthorized Traffic

PC-B (10.10.10.11)

```bash
ping 10.10.12.10
```

Result:

Blocked

PC-D (10.10.11.11)

```bash
ping 10.10.12.10
```

Result:

Blocked

These results confirm that the firewall successfully prevents unauthorized communication.

---

## Firewall Verification

The following commands were used to verify firewall operation:

```bash
show zone security
show zone-pair security
```

These commands confirm that:

* Security zones are active.
* Zone pairs are configured correctly.
* Traffic inspection policies are applied.

---

## Key Learning Outcomes

Through this project, I gained practical experience in:

* Cisco IOS configuration
* Dynamic routing with RIP Version 2
* Zone-Based Firewall deployment
* Security policy implementation
* Traffic inspection concepts
* Network troubleshooting and verification

---

## Repository Contents

* Packet Tracer Project File (.pkt)
* Project Documentation
* Topology Screenshot
* Configuration Verification Results

---

## Author

Sithila Sathsara Gamage

Networking | Cybersecurity | Cisco Technologies

Feel free to explore the project and share any suggestions or feedback.
