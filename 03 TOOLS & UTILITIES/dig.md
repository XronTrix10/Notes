# ⚙️ dig
Tags: #⚙️ 
Related to: 
See also: [[dns zone transfer]], [[dns cache snooping]], [[whois]]
Previous: 

---
## Description
DNS lookup utility.

## Usage Examples
### Zone Transfer
	dig @[server] [domain] AXFR

### Incremental Zone Transfer
dig can perform an incremental zone transfer, pulling only recently updated records  
(N is an integer that refers to the serial number of a Start of Authority record.  
The incremental zone transfer request will pull all records that have changed since  
the SOA serial number was the N we specified):

	dig @[server] [domain] -t IXFR=[N]
  
---
## References
- [[]]