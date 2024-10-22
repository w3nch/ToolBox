# Suricata: Free and Open-Source IDS, IPS, and Network Monitoring

Suricata is a **free and open-source Intrusion Detection System (IDS)**, **Intrusion Prevention System (IPS)**, and **network monitoring tool** developed and maintained by the **community-run Open Information Security Foundation (OISF)**.

## Main Operational Modes of Suricata:

1. **Active Mode (IDS)**:
   - Suricata works in active mode as an **Intrusion Detection System (IDS)**. In this mode, it **monitors** network traffic, detecting threats and generating alerts without blocking or stopping the traffic.

2. **Passive Mode (IPS)**:
   - In passive mode, Suricata functions as an **Intrusion Prevention System (IPS)**, where it not only detects threats but also **takes preventive actions** like blocking malicious traffic to stop potential attacks in real-time.


Installation

``` bash
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:oisf/suricata-stable
sudo apt-get update
sudo apt-get install suricata
```

To upgrade Suricata to the latest version, run the following commands:

``` bash
sudo apt-get update
sudo apt-get upgrade suricata
```

Removing Suricata

```bash
sudo apt-get remove suricata
```

For further information on Suricata and its setup, you can visit the official OISF Launchpad.
