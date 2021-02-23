# 7.0 Active Information Gathering

## 7.1 DNS Enumeration

### 7.0.0 DNS Query Procedure
![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/dns_routine_map.jpg.png)

### 7.0.1 DNS Record format
	<name> : The forst field contains the domain name.
	<ttl> : Time to live specifies how long the information is guaranteed to be valid.
	<class> : The class field specifies the type of network
	<type> : The DNS record type (MX,A,NS, etc..)
	<priority> : The smaller the value, the higher the server's priority.
	<rdata> : Resource data defines the mail server name.

### 7.0.2 DNS Server record types
- **NS** : Nameserver records contain the name of the authoritative servers which are hosting the DNS records for a domain.(Resides in TLD DNS Servers)
- **A** : Also known as a host record, the "a record" contains the IP address of a hostname such as www.megacorpone.com (Resides in authoritative name servers)
- **MX** :  Mail Exchange records contain the names of the servers responsible for handling email for the domain. A domain can contain multiple MX records.(Example : for www.google.com 
- **PTR** : Pointer Records are used in reverse lookup zones and are used to find the records associated with an IP address.
- **CNAME** : Canonical Name Records are used to create aliases for the host records.
- **TXT** : Text records can contain any arbitary data and can be used for various purposes, such as domain ownership verification.

To demonstrate those types we could use `host <hostname>` command.

- `host www.megacorpone.com` - forward lookup
- `host -t <type> megacorpone.com` 
- `host <ip_address>` - reverse lookup



