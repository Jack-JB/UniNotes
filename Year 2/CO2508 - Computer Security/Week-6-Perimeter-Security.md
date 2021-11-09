# Perimeter Security

## Introduction

- A network perimeter is an imaginary line drawn around a set of resources that you want to protect (aka the security domain)
- Modern working practices require the perimeter to be flexible; and often nowadays to go beyond the control of the security officer
  - For example BYOD, or remote working

## Network Address Translation (NAT)

- NAT isn't typically considered to be a security operation of a network
  - Yet it does provide security features - by hiding the existence of computers on the network behind public IP addresses

## Firewall

- A firewall is the most basic form of perimeter security

  - Provides a 'barrier' for network traffic going in or out of your network

    - Examines data packets and either:

      - Allows seemingly good packets
      - Dropping recognisably bad packets & logging this action

    - Examines data packets and only lets through 'good' packets (filtering)

      - Ingress filtering: Data packets entering the network
      - Egress filtering: Data packets exiting the network

      ​	

- What are good and back traffic/packet?

  - Bad traffic  = something we already know is bad
  - Good traffic = something that might be either good or bad
    - We don't *yet* know it is bad
    - Once we learn about it - we might realise it is bad

- Notice that firewalls do not remove the risk of bad traffic entirely

### Firewall Classification

- Two different types of firewall
  - Host-based firewall
    - Protects an individual host/computer/device
  - Network-based firewall
    - Protects a range of hosts/computers/devices connected to a network
  - A mixture of both is best

### Stateless Packet Filtering

- An early generation firewall filtering mechanism

  - Allow/deny traffic paths based on filtering rules
  - Uses **only** the filtering rules to make decision
  - Checks the connection each time data is sent/received

  - Doesn't remember previous allowed communication/conversation
    - Doesn't know if this communication is part of a conversation that has already started



- Early generation and vulnerable to certain types of attacks
  - For example, the teardrop DoS attack
    - This attack used large data packets that had been fragmented, when rebuilding them afterwards they can be set to overlap and extend beyond the allowed data packet size
    - A stateless firewall was vulnerable to such an attack because it didn't 'remember' the previous data fragment size

### Stateful Packet Filtering

- An improvement on stateless, stateful is able to remember if individual communications are part of an ongoing conversation
  - Still applies the same allow/deny rules specified in the filter rules
  - Remembers if an individual communication is part of an on going conversation
    - This allows the firewall to detect if someone attempts to emulate part of a conversation, designed to get passed the firewall rules



- Newer than stateless, and able to detect more types of attacks
  - Earlier we talked about the SYN attack
  - A TCP handshake consists of "SYN = ACK-SYN = ACK"
    - A SYN attack withholds the last SYN and leaves the handshake incomplete
  - A stateful will know about the handshake data packets
  - Will detect a missing ACK and terminate the conversation

### Packet Filters / Rules

- A set of explicit rules that describe allowed network paths
  - An Access Control List (ACL) is a set of rules that allow or deny data
  - Works by examining the packets header content
  - Compares the header content against these explicit rules

- The packet filter rules can be customised around several conditions
  - IP Addresses
  - Domain names
  - Protocols
  - Ports
  - Specific keywords and OS'

- Deciding which data can enter/leave a network is complex
  - Accept all - dangerous, and will allow malicious data into the network
  - Reject all - might stop the data you want on your network - however, see below this should be the default rule
  - Rules work on top to bottom basis
    - Start at top and move down the list until a matching rule
  - The last rule should block by default
    - Add new rules as service needs become apparent
      - E.g. add port 80 (web server) if you start to provide web server functionality on your network

> - The SANS Institute recommend setting rules in the following order ...
>   - - Anti-spoofing filters (blocked private addresses, internal addresses)
>     - User permitted rules (e.g. allow HTTP to public web server)
>     - Management permit rules (e.g. SNMP traps)
>     - Noise drops
>     - Deny and alert (alerts admin about suspicious traffic)
>     - Deny and log (log remaining traffic for analysis)

### Application Layer Gateway

- Firewalls could be setup to enable application services
  - e.g. HTTP, FTP Bit torrent
  - Rather than requiring the administrator detailed knowledge of what ports are needed by the software, they came predefined on the firewall
    - Need to be updated
    - Not as efficient - more inspection operations needed

## Security Domain?

- What is Security Domain?

  - Any group of computers, networks or infrastructure that falls within a security perimeter
  - A security domain may be
    - '**Fixed**' in which different users have access to the same elements within that security domain
    - '**Flexible**' where different users have access to different elements within that security domain

  - Access to the security domain is normally determined through a user authentication process
    - Which determines where the perimeter is for that user

## Demilitarised Zone (DMZ)

- It is not sensible to have a  'monolithic firewall' setup

  - Sometimes you want to allow different access levels for internal and external traffic

  - If you have resources available to the 'general public' then these would have different level of availability and different security rules would apply

  - Creating a 'no mans land' or 'demilitarised zone' between the public internet and private LAN network

    - allows access to resources available to general public
    - Denies access to resources available internally only

    

