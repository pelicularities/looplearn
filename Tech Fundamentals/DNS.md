Domain Name System: converts domain names to IP addresses

Type name into browser, e.g. www.netflix.com
Computer asks DNS for IP address
Computer then requests data from computer at IP address

Why is DNS distributed instead of centralised?
- resiliency
- scaling

DNS Zone: a database containing records
ZoneFile: a file storing the zone on disk

DNS servers hosts 1+ zones by storing 1+ ZoneFiles

Authoritative: for a given domain, stores the real, authoritative records

Non-authoritative/cached: copies of records / zones

DNS Root: this is a zone
- every server knows about and trusts the DNS root zone
- management of the root zone is handled by IANA
- management of the hardware hosting the root zone is handled by a variety of organisations, each one managing one of the 13 IP addresses representing the root zone, e.g. ICANN, NASA, UMD, Verisign

Chain of trust
root zone -> .com zone -> netflix.com zone

