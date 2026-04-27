# Network Delay Analysis with Docker

## Overview
This project analyzes end-to-end network delay using a multi-router network simulated with Docker.

## Technologies Used
- Docker
- Linux tc (traffic control)
- ICMP (ping)
- Networking concepts (transmission, propagation, queuing delay)

## How to Run

1. Start the Docker network:
   docker-compose -f LAN-3R2H.yml up -d

2. Configure network delays using tc commands (see report for full commands)

3. Generate traffic using ping:
   ping -l 10 -c 20 -s 1232 <destination-ip>

4. Capture packets using tcpdump to observe delays

## Results (Screenshots)

![Packet Capture](network-capture.png)

The screenshot shows ICMP traffic during the simulation. 
Packets are transmitted at different rates, demonstrating queue buildup and delay across routers.

## Delay Calculation Table

The full packet-by-packet delay computation is provided in the files below:

[View Delay Table (PDF)](HW-01-Delay-Table-Example.pdf)

These tables show how transmission delay, propagation delay, and queuing delay were calculated for each packet across all routers.

## What I Learned
I learned how end-to-end delay is composed of transmission, propagation, and queuing delay, and how congestion builds when arrival rate exceeds service rate.

## Challenges
One challenge was correctly interpreting the assignment requirements and fixing incorrect delay calculations. Another challenge was configuring Docker and clearing incorrect tc settings.
