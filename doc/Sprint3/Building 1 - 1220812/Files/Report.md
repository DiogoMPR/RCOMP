# Building 1

## Specifications

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

- At this sprint each team member should use as a starting point the overall simulation resulting from sprint 2 (campus.pkt), nevertheless, each team member will oversee the same building as before.
- Each team member must:

      - change from static routing to OSPF based dynamic routing in every existing router.

      - add a new server to the local DMZ network and create a simple HTML page, in each building.

      - the router in each building must provide the SHCPv4 service to all IPv4 networks within a building, with the exception of DMZ networks and the backbone.

      - in the VoIP VLAN, the DHCP server configuration must include option 150.

      - in the simulation, for VoIP local testing, in each building there should be at least two connected IP phones (of 7960 model). Ports of switches connecting to Cisco IP phones 7960, must have the voice
      VLAN enabled (switchport voice vlan VLANID) and the access VLAN disabled (no switchport access vlan).

      - one DNS domain is going to be established on each building.

- The team member in charge of building 1 will create a DNS domain name matching the team’s
  repository name (rcomp-23-24-dd-g2). This is going to be the highest-level domain, so it’s going to
  be used as if it was the DNS root domain. It must t know the IPv4 addresses
  of the name servers of its subdomains (each one in each of the other buildings).
-  Knowing a name server that is out of the scope of
   the local domain requires in fact two DNS records:

        - The NS record itself: the record’s name is the domain’s name, and the record’s data is the DNS
        name of the name server of that domain.

        - The A record for the NS record: the record’s name is the DNS name of the name server and
        the record’s data is the IPv4 address the name server.

  - All HTTP servers are to be named as server1. Within each DNS domain there should be:

        - a www alias (CNAME) mapped to the same domain’s server1 A record.
  
        - an alias, named web also mapped to the domain’s server1 A record.
  
        - one additional alias (CNAME), with name dns, and mapped to the domain’s ns A record, should also
        exist.

- All end-nodes within a building should be using the local DNS name server, and, if supported, have the
  default DNS domain name set to the local DNS domain name.

      - For end-nodes with automatic DHCP configuration, that information should be inserted into the local
      DHCP pools.

      - For end-nodes with static manual configuration, such as servers, that information must be added manually.

- HTTP and HTTPS requests received in the router’s backbone interface must be redirected to the DNS server
  in the local DMZ. Both HTTP and HTTPS use TCP connections, the default service ports numbers must be 80 and 443.

- The HTTP/HTTPS service on the DNS server must be enabled and must be created a simple HTML page identifying it.

- Traffic access policies (which packets are allowed or not) must be implemented in routers. They will be particularly restrictive on traffic exchanged with the
  local DMZ, and traffic that is intended to the router itself.

- Output:

      - Packet Tracer simulation file for the corresponding building, it should be named building1.pkt

      - document detailing DNS databases records on the building’s DNS name server, it may be a screenshot of the server’s DNS database.

      - a text file with a configuration dump for every switch and for every router within the encompassed building.


## OSPF dynamic routing

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

- Static routing is no longer used, therefore, in each router the existing static routing tables were deleted, except for the default route that connects to the ISP (since without this route there would be no internet distribution on campus). 
- The overall infrastructure is now an OSPF domain being divided into OSPF areas, one for each building and the backbone area (area 0).

### Building 1 router configuration:

    router ospf 1
    network 172.22.108.128 0.0.0.127 area 1
    network 172.22.109.0 0.0.0.127 area 1
    network 172.22.109.128 0.0.0.63 area 1
    network 172.22.109.192 0.0.0.63 area 1
    network 172.22.108.0 0.0.0.127 area 1
    network 172.22.110.0 0.0.0.255 area 0
    default-information originate

* The "default-information originate" command is used in the OSPF routing protocol to insert the default route to point to the ISP router.

## HTTP servers

------------------------------------------------

- Another server was added to the DMZ VLAN to take over the HTTP service.
- In the services of this server, the HTTP service was enabled and a simple HTML page was added identifying the building.

![html_page.png](..%2FImages%2Fhtml_page.png)

----------------------------------------

## DHCPv4 service

----------------------------------

- Each building's router provides DHCPv4 service to all local networks (within the building), except for DMZ and backbone networks, where IPv4 addresses are static and manually defined. 
- For the VoIP VLAN, the DHCP server configuration includes option 150, which represents the IP address of the TFTP (Trivial File Transfer Protocol) server to be used by the phones. 
- All computers and laptops now receive network configuration via DHCP.

### Floor 0

     ip dhcp pool GroundFloor1
      network 172.22.109.128 255.255.255.192
      default-router 172.22.109.129
      dns-server 172.22.108.2
      domain-name rcomp-23-24-dd-g2

### Floor 1

    ip dhcp pool FloorOne1
      network 172.22.109.192 255.255.255.192
      default-router 172.22.109.193
      dns-server 172.22.108.2
      domain-name rcomp-23-24-dd-g2

### Wi-fi

    ip dhcp pool Wifi1
      network 172.22.108.128 255.255.255.128
      default-router 172.22.108.129
      dns-server 172.22.108.2
      domain-name rcomp-23-24-dd-g2

### VoIP

    ip dhcp pool VoIP1
      network 172.22.109.0 255.255.255.128
      default-router 172.22.109.1
      option 150 ip 172.22.109.1
      dns-server 172.22.108.2
      domain-name rcomp-23-24-dd-g2

### Removing gateway addresses

    ip dhcp excluded-address 172.22.108.129
    ip dhcp excluded-address 172.22.109.1
    ip dhcp excluded-address 172.22.109.129
    ip dhcp excluded-address 172.22.109.193

## VoIP service

-----------

### Switches configuration

- On the ports of the switches that connect to the telephones, the voice VLAN is activated and the access VLAN is deactivated.

### Automatic phone registration and directory number assignment

- As DHCP was already configured, it was only necessary to configure the telephone service and each person's telephone number on the building's router.

      telephony-service
      auto-reg-ephone
      ip source-address 172.22.109.1 port 2000
      max-ephones 20
      max-dn 20

      ephone-dn 1
      number 1000
      
      ephone-dn 2
      number 1001

### Call forwarding

- For calls between buildings, the dial-peer voice command was used. Each pattern is forwarded to the respective building's router.

      dial-peer voice 372 voip
      destination-pattern 2...
      session target ipv4:172.22.110.2
      
      dial-peer voice 377 voip
      destination-pattern 3...
      session target ipv4:172.22.110.3
    
      dial-peer voice 382 voip
      destination-pattern 4...
      session target ipv4:172.22.110.4

- Because VoIP phones have been added and configured on the network, they can now communicate with each other.

![telephones.png](..%2FImages%2Ftelephones.png)

## DNS

-----------

- The server placed in the last sprint is used as a DNS server.

- Within the DNS database, all names are FQDN (fully qualified domain names), so all defined names end with rcomp-23-24-dd-g2.

- The HTTP server was named server1 (A record). Within the DNS domain, there are two aliases www and web (CNAME), both mapped to server1 (A record) of the same domain. There is an additional nickname, with the name dns (CNAME), mapped to the domain ns (A record).

- On the servers, the IPv4 of the DNS server was manually added.

### DNS table configured on server 1 of building 1 (Server_DNS_1):

![DNSTable.png](..%2FImages%2FDNSTable.png)

## NAT (Network Address Translation)

-------------------------------------

- Static NAT was used to redirect traffic, so the requested settings were applied to the building's router.

- HTTP and HTTPS requests received on the router's backbone interface are redirected to the HTTP server in the local DMZ. Both HTTP and HTTPS use TCP connections and assume the service's default port numbers are used, 80 and 443.

      ip nat inside source static tcp 172.22.108.3 80 172.22.110.1 80
      ip nat inside source static tcp 172.22.108.3 443 172.22.110.1 443

- DNS requests received on the router's backbone interface are redirected to the DNS server in the local DMZ. The DNS service uses TCP and UDP connections, in both cases the service's default port number is 53.

      ip nat inside source static tcp 172.22.108.2 53 172.22.110.1 53
      ip nat inside source static udp 172.22.108.2 53 172.22.110.1 53

- Each VLAN was placed within the created NAT, except the backbone.

      interface FastEthernet1/0.362
      ip nat outside

      interface FastEthernet1/0.363
      ip nat inside

      interface FastEthernet1/0.364
      ip nat inside

      interface FastEthernet1/0.365
      ip nat inside

      interface FastEthernet1/0.366
      ip nat inside

## Static Firewall (ACLs)

-------------------------------------

### Backbone

    access-list 100 deny ip any host 172.22.109.129
    access-list 100 permit ip any 172.22.109.128 0.0.0.63
    access-list 100 deny ip 172.22.109.192 0.0.0.63 any
    access-list 100 deny ip any host 172.22.109.193
    access-list 100 permit ip any 172.22.109.192 0.0.0.63
    access-list 100 deny ip any host 172.22.108.1
    access-list 100 permit icmp any 172.22.108.0 0.0.0.127 echo-reply
    access-list 100 permit ospf any any

### Floor 0

    access-list 104 deny ip any host 172.22.108.1
    access-list 104 deny ip any host 172.22.108.129
    access-list 104 deny ip any host 172.22.109.1
    access-list 104 deny ip any host 172.22.109.129
    access-list 104 deny ip any host 172.22.109.193
    access-list 104 permit icmp any 172.22.108.0 0.0.0.127 echo-reply
    access-list 104 permit tcp any 172.22.108.0 0.0.0.127 eq www
    access-list 104 permit tcp any 172.22.108.0 0.0.0.127 eq 443
    access-list 104 permit udp any 172.22.108.0 0.0.0.127 eq domain
    access-list 104 deny ip any 172.22.108.0 0.0.0.127
    access-list 104 permit ip 172.22.109.128 0.0.0.63 any
    access-list 104 permit udp any eq bootpc any eq bootps

### Floor 1

    access-list 105 deny ip any host 172.22.108.1
    access-list 105 deny ip any host 172.22.108.129
    access-list 105 deny ip any host 172.22.109.1
    access-list 105 deny ip any host 172.22.109.129
    access-list 105 deny ip any host 172.22.109.193
    access-list 105 permit icmp any 172.22.108.0 0.0.0.127 echo-reply
    access-list 105 permit tcp any 172.22.108.0 0.0.0.127 eq www
    access-list 105 permit tcp any 172.22.108.0 0.0.0.127 eq 443
    access-list 105 permit udp any 172.22.108.0 0.0.0.127 eq domain
    access-list 105 deny ip any 172.22.108.0 0.0.0.127
    access-list 105 permit ip 172.22.109.192 0.0.0.63 any
    access-list 105 permit udp any eq bootpc any eq bootps

### Wi-fi

    access-list 102 deny ip any host 172.22.108.1
    access-list 102 deny ip any host 172.22.108.129
    access-list 102 deny ip any host 172.22.109.1
    access-list 102 deny ip any host 172.22.109.129
    access-list 102 deny ip any host 172.22.109.193
    access-list 102 permit icmp any 172.22.108.0 0.0.0.127 echo-reply
    access-list 102 permit tcp any 172.22.108.0 0.0.0.127 eq www
    access-list 102 permit tcp any 172.22.108.0 0.0.0.127 eq 443
    access-list 102 permit udp any 172.22.108.0 0.0.0.127 eq domain
    access-list 102 deny ip any 172.22.108.0 0.0.0.127
    access-list 102 permit ip 172.22.108.128 0.0.0.127 any
    access-list 102 permit udp any eq bootpc any eq bootps

### VoIP

      access-list 103 deny ip any host 172.22.108.1
      access-list 103 deny ip any host 172.22.108.129
      access-list 103 deny ip any host 172.22.109.1
      access-list 103 deny ip any host 172.22.109.129
      access-list 103 deny ip any host 172.22.109.193
      access-list 103 permit icmp any 172.22.108.0 0.0.0.127 echo-reply
      access-list 103 permit tcp any 172.22.108.0 0.0.0.127 eq www
      access-list 103 permit tcp any 172.22.108.0 0.0.0.127 eq 443
      access-list 103 permit udp any 172.22.108.0 0.0.0.127 eq domain
      access-list 103 deny ip any 172.22.108.0 0.0.0.127
      access-list 103 permit ip 172.22.109.0 0.0.0.127 any
      access-list 103 permit udp any eq bootpc any eq bootps

### Grouping of ACLs 

    interface FastEthernet1/0.2
      ip access-group 102 in

    interface FastEthernet1/0.3
      ip access-group 103 in

    interface FastEthernet1/0.4
      ip access-group 104 in


    interface FastEthernet1/0.5
      ip access-group 105 in

    interface FastEthernet1/0.6
      ip access-group 100 in