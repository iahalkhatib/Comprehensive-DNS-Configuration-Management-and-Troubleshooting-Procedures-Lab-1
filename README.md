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

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/3270e8ff-1406-443b-9468-5d7cca409add)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/c94ed8f4-ee00-402a-a7a1-e72dc589f487)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/bc7387d9-ae6a-49ac-aee2-e8925625d48b)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/57c662b0-1781-4234-986d-452578b1b3f5)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/707a8b3b-9e72-41a9-af75-93798dac9f0d)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/7bbe869a-0b5a-4915-b248-c3f9a43ca1ed)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/d92aa78d-4a26-4214-9f13-9080d95bd123)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/9524809f-7fd6-4214-a394-3c2eb320d154)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/ce9e5890-5477-4185-86dd-a70d5d17f213)

Go back to Client-1 and try to ping it. Observe that it works





# Task 2. Local DNS Cache Exercise

Go back to DC-1 and change mainframe’s record address to 8.8.8.8

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/1090eb8e-3d46-4bad-8878-17a9b0a123e4)

Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/3e19541e-709b-4a78-889a-9369348d1d5e)

Observe the local dns cache (ipconfig /displaydns) 

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/8854e499-d3ba-4720-b68e-96f63214357f)

Flush the DNS cache (ipconfig /flushdns). Observe that the cache is empty

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/31c2025b-16fb-4d4a-b90d-a3be1b13b057)
![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/5c6719c8-ab80-4a39-adb2-f44418ba28f5)

Attempt to ping “mainframe” again. Observe the address of the new record is showing up
![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/0cd99038-8f99-4b3a-8790-7e08adad202e)

# Task 3. CNAME Record Exercise

Go back to DC-1 and create a CNAME record that points the host “search” to “www.google.com”

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/201c9b67-b6a7-484a-82d0-52d40ef4cff4)

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/44ab1aca-2cfc-4a58-ba9f-731034b01816)

Go back to Client-1 and attempt to ping “search”, observe the results of the CNAME record

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/ede78e78-6225-4dbd-b68b-cbf051b27e7f)

On Client-1, nslookup “search”, observe the results of the CNAME record

![image](https://github.com/iahalkhatib/Comprehensive-DNS-Configuration-Management-and-Troubleshooting-Procedures-Lab-1/assets/170050432/0ed3b650-aad2-4b46-a0be-4e3609c5f98c)
