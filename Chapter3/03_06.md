## 📚 Table of Contents

- [5G Auth Flow Security Lab](#-5g-security-lab-investigating-authentication-flows--threat-detection)
  - [Learning Goal](#learning-goal)
  - [Prerequisites](#prerequisites)
  - [Step 1: Capture 5G Authentication Flows](#step-1-capture-5g-authentication-flows)
  - [Step 2: Analyze Security Parameters](#step-2-analyze-security-parameters)
  - [Step 3: Replay Attack Simulation](#step-3-replay-attack-simulation)
  - [Step 4: TTP Mapping Table](#step-4-ttp-mapping-table)
  - [Deliverables](#expected-deliverables)

- [5G NRF Security Lab](#-5g-nrf-security-lab-evaluating-secure-nf-registration-and-discovery-with-tls-and-oauth2)
  - [Learning Goal](#learning-goal-1)
  - [Step-by-Step Activities](#step-1-discover-network-functions)
  - [Deliverables](#deliverables-1)
 

    Evaluating Secure NF Registration and Discovery with TLS and OAuth2

    Prerequisites

-Working Open5GS with NRF, AMF, SMF deployed in Kubernetes

-curl with HTTP/2 support

-TLS certificates enabled for NRF (or use plain HTTP for contrast)

-Optionally: NRF with and without OAuth2 enabled

 Discover Network Functions

Use curl to query NRF from inside a pod:
curl -k -H "Accept: application/json" \
  https://<nrf-ip>:<port>/nnrf-nfm/v1/nf-instances





