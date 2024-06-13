![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/2c78788f-aff0-4010-8da7-f3dea1d85dd7)

# Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1



# Task 1. A-Record Exercise

Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin) using RDP

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/cc260045-f9fc-4302-84d3-b5b970f85c36)

Connect/log into Client-1 as an admin (mydomain\jane_admin)

From Client-1 try to ping “mainframe” notice that it fails

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/6b55d99e-f110-4ab3-95b8-e7b3511d48a3)

Nslookup “mainframe” notice that it fails (no DNS record)


Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address


Go back to Client-1 and try to ping it. Observe that it works





Local DNS Cache Exercise
Go back to DC-1 and change mainframe’s record address to 8.8.8.8
Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address
Observe the local dns cache (ipconfig /displaydns)
Flush the DNS cache (ipconfig /flushdns). Observe that the cache is empty
Attempt to ping “mainframe” again. Observe the address of the new record is showing up

CNAME Record Exercise
Go back to DC-1 and create a CNAME record that points the host “search” to “www.google.com”
Go back to Client-1 and attempt to ping “search”, observe the results of the CNAME record
On Client-1, nslookup “search”, observe the results of the CNAME record
