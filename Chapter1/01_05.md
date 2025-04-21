
Step-by-Step Guide for testing UE, GNB, Registration message and traces

Step 0: Capture and Analyze Logs 

1. Start a packet capture on the instance: 

   sudo tcpdump -i any -w /home/ubuntu/reg.pcap 

2. Install and open Wireshark: 

   sudo apt install wireshark 

   wireshark reg.pcap 

Step 1: UERANSIM Setup and Execution 

1. Navigate to the UERANSIM build directory: 

   cd /root/UERANSIM/build/ 

2. Open two tabs or terminal windows: 

   - Tab 1: Run gNB: 

     ./nr-gnb -c ../config/open5gs-gnb.yaml 

   - Tab 2: Run UE: 

     ./nr-ue -c ../config/open5gs-ue.yaml 

3. Use IMSI `208930000000001` and default cell ID if needed. 

Step 2: Test Connectivity 

1. From the UE terminal, check internet connectivity: 

   ping -I uesimtun0 google.com 
