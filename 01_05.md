# ☁️ 5G Lab: UE Registration, Traffic Capture & Monitoring with Open5GS

> This lab guides you through validating **UE registration**, capturing **5G signaling/user-plane traffic**, and analyzing system behavior using **Prometheus**, **Grafana**, and the **EFK logging stack** — all within a **pre-configured Open5GS and UERANSIM environment**.

---

## 🎯 Learning Goal

**With this content, you will be able to** validate UE registration in a pre-configured Open5GS environment, capture 5G signaling and user traffic using Wireshark, and analyze system behavior through Prometheus-Grafana monitoring and EFK-based log inspection.

---

## 📌 Prerequisites

Before starting this lab, ensure you have access to a **configured lab environment** that includes:

- Open5GS core network (already deployed)
- UERANSIM components with gNB and UE configuration
- Prometheus & Grafana stack installed and accessible
- EFK (Elasticsearch, Fluentd, Kibana) stack installed
- Basic Linux terminal access with root/sudo privileges

> ⚠️ This guide assumes the lab environment is already up and running. Deployment instructions are not included.

---

## 🚀 5G Stack Components

### 🧩 Open5GS

- **Repo:** [Open5GS GitHub](https://github.com/open5gs/open5gs/)
- **Docs:** [Open5GS Documentation](https://open5gs.org/open5gs/docs/)
- **Typical Path:** `/home/ubuntu/codebase/5gcore/open5gs`

---

### 📶 UERANSIM

- **Repo:** [UERANSIM GitHub](https://github.com/aligungr/UERANSIM)
- **Docs:** [UERANSIM Wiki](https://github.com/aligungr/UERANSIM/wiki/Usage)

- UE Registration & Connectivity Test

- # Terminal 1 - gNB
cd /root/UERANSIM/build/
./nr-gnb -c ../config/open5gs-gnb.yaml

- # Terminal 2 - UE
./nr-ue -c ../config/open5gs-ue.yaml

- **Example Commands:**

```bash
# Run gNB
./nr-gnb -c config/open5gs-gnb.yaml

# Run UE
./nr-ue -c config/open5gs-ue.yaml

- **

./nr-cli imsi-208930000000001
./nr-cli --dump
ping -I uesimtun0 google.com
sudo curl --interface uesimtun0 google.com

🧪 Wireshark & Packet Capture
📦 Capture Packets with tcpdump

# Capture all interfaces and save to file
sudo tcpdump -i any -w /home/ubuntu/reg.pcap

Analyze with Wireshark

# If not installed
sudo apt update && sudo apt install wireshark

# Open capture file
wireshark /home/ubuntu/reg.pcap


- ## 📊 Prometheus & Grafana Monitoring
- ##🚀 Prometheus & Grafana Startup

cd /home/ubuntu/codebase/monitoring/
./installPromGrafana.sh

To Stop Services
./uninstallPromGrafana.sh


Access Grafana Dashboard

http://<your-lab-ip>:3000

http://<your-lab-ip>:3000


cd /home/ubuntu/codebase/efk/
./InstallEFKStack.sh

Stop Logging Stack

./UninstallEFKStack.sh

View Logs
If deployed on Kubernetes:

kubectl get pods -n open5gs
kubectl logs <pod-name> -n open5gs

You can also log into Kibana (default port: 5601) and search logs using structured fields (e.g., container name, log level).





