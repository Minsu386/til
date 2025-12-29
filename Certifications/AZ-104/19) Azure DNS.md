Domain Name System (DNS) it is a service that is responsible for translating (or resolving) a service name to its IP address

Azure DNS is a hosting service for DNS domains that provides name resolution by using Microsoft Azure Infrastructure
- You CAN'T use Azure DNS to buy a domain name

Public DNS internet-facing
- Allows you to manage domains for internet-accessible domains
    - Pointing your domain to your website
    - Setting records to prove you own the domain
    - Records to connect you domain to your email server

 Private DNS internal-facing
 - Allows you to use your own custom domains instead of the Azure Provided domains

DNS Zone is a container for all your DNS records for a specific domain name

DNS Record is a rule that says where to send your domain name. A record is compose of name, type and value:
- An **Address** lets you point your domain to an IPv4 address
- **AAAA** lets you point your domain to an IPv6 address
- **CAA** Certificate Authorities (CAs) records authorized who can issue certificates for their domain
- **CNAME** Canonical Name Records creates an alias from one domain to another so you set the record value to a domain
- **MX** Mail Exchange records point to mail servers that handle emails
- **NS** Name Server records identify multiple DNS servers for the domain and there are multiple in case the primary DNS server fails
- **PTR** Pointer record points to a domain or hostname but is used for reverse DNS lookup
- **SRV** Service record is used to identify computers that hose specific services, like locating Domain Controllers for Active Directory
- **TXT** Text records are just text and can serve multiple purposes, such as documentation or as a means of verification
- **SOA** State of Authority record contains administrative details about a domain

Azure has its own special record type called an Alias that work with A, AAAA, and CNAME records
- Azure Alias record points directly to an Azure resource instead of an IP or hostname  (helps avoid dangling domains)

Record  Set A group of records. Azure always creates a record set, even with a single record

Time to Live (TTL) says how long a value should be cached