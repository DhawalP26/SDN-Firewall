# SDN-Based Firewall using Mininet and POX

## Objective
To implement an SDN-based firewall using Mininet and POX controller that demonstrates rule-based packet filtering.

## Tools Used
- Mininet
- POX Controller
- OpenFlow Protocol

## Topology
- 1 Switch (s1)
- 3 Hosts (h1, h2, h3)
- 1 Controller (POX)

## Working
The controller listens for packet_in events and applies firewall rules based on IP addresses.  
If a rule matches, the packet is dropped; otherwise, it is forwarded.
The controller uses OpenFlow match-action rules to inspect packet headers and decide whether to drop or forward packets dynamically.

## Firewall Rules
- Allow traffic between h1 and h2
- Block traffic from h1 to h3

## Steps to Run

### 1. Start Controller: python3 pox.py firewall
### 2. Start Mininet: sudo mn --topo single,3 --controller=remote,ip=127.0.0.1,port=6633
### 3. Test: 
  h1 ping h2 # Allowed
  h1 ping h3 # Blocked

## Expected Output
- h1 ↔ h2: Successful communication
- h1 → h3: Packet loss (blocked)

## Results
- Selective packet filtering achieved
- Firewall rules enforced correctly
- Network behavior verified using ping and pingall

## Conclusion
This project demonstrates how SDN enables dynamic traffic control using centralized controllers and programmable rules.
