# Cisco Packet Tracer Network Troubleshooting

## Objective

To identify and troubleshoot common network connectivity problems using Cisco Packet Tracer by analyzing issues at OSI Layers 1, 2, and 3.

---

## Network Topology

PC0 ---- Switch0 ---- PC1

---

## IP Address Configuration

| Device | IP Address | Subnet Mask |
|----------|----------|----------|
| PC0 | 192.168.10.25 | 255.255.255.0 |
| PC1 | 192.168.10.26 | 255.255.255.0 |

---

## Successful Ping Test

Command:

```bash
ping 192.168.10.26
```

Result:

- Packets Sent: 4
- Packets Received: 4
- Packet Loss: 0%

This confirms successful connectivity.

---

## Error Scenario 1: Mismatched Subnet

Configuration:

PC0: 192.168.10.25/24

PC1: 192.168.20.26/24

Command:

```bash
ping 192.168.20.26
```

Result:

- Request timed out
- 100% packet loss

Cause:

Hosts were configured in different subnets without a router.

OSI Layer:

Layer 3 (Network Layer)

---

## Error Scenario 2: Physical Layer Failure

Action:

Disconnected the cable between PC0 and Switch0.

Result:

- Ping failed
- 100% packet loss

OSI Layer:

Layer 1 (Physical Layer)

---

## ARP Verification

Command:

```bash
arp -a
```

Observation:

The ARP table displayed the MAC address associated with PC1.

Purpose:

ARP resolves IP addresses into MAC addresses for Layer 2 communication.

---

## Simulation Mode Analysis

Simulation Mode was used to observe ICMP and ARP packets moving through the network.

The Capture/Forward feature helped identify packet flow and packet drops during troubleshooting.

---

## Conclusion

The experiment demonstrated how network problems can be diagnosed using ping, ARP, and Packet Tracer Simulation Mode. Physical and logical connectivity issues were successfully identified and resolved using a systematic troubleshooting approach.