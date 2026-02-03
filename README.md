# Network-Security-Foundations

Project Overview This repository contains a series of laboratory exercises focused on core networking principles, including Layer 2 switching, Layer 3 routing, and gateway configuration. These labs were designed to simulate real-world office network environments using Cisco Packet Tracer.

Lab 1: Layer 2 MAC Discovery Objective: Observe the dynamic population of a Layer 2 Switch's CAM (Content Addressable Memory) table.

The Process: Initially, the switch has no record of connected devices. By initiating ICMP traffic (Ping), the switch "listens" to the source MAC addresses.

Observation: After a successful ping between PC0 and PC1, the switch dynamically mapped the MAC addresses to ports Fa0/1 and Fa0/2.

Figure 1: Verified CAM table state showing learned MAC addresses after network traffic.

Lab 2: Inter-Subnet Communication Failure The Problem: Testing the boundaries of a Layer 2 domain.

Finding: Communication between the 192.168.1.x and 10.x.x.x subnets failed despite a healthy physical connection to the same switch.

Technical Reason: Without a Layer 3 Gateway, devices cannot route traffic outside their local subnet boundaries. This lab proves that switches operate purely on physical addresses and do not understand logical IP routing.

Figure 2: ICMP failure (Request Timed Out) demonstrating logical network isolation.

Lab 3: Inter-Subnet Routing & Gateway Configuration

Objective: Restore connectivity between isolated subnets using a Cisco 2911 Router.

Key Configuration: * Assigned Virtual Interface IPs (Gateways) on the router.

Configured Default Gateways on all end-devices to provide an "exit path" for non-local traffic.

Outcome: Achieved 100% end-to-end connectivity.

Figure 3: Successful ping across subnets after establishing a Layer 3 path.

Challenges Faced & Debugging During the initial setup of Lab 3, the ping to 10.0.0.1 failed consistently. Through systematic troubleshooting, I identified that the Default Gateway on the source PC was missing. This prevented the return traffic from finding its way back. Correcting this resolved the issue and solidified my understanding of bidirectional traffic flow.
