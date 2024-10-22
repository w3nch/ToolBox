# Suricata: Free and Open-Source IDS, IPS, and Network Monitoring

Suricata is a **free and open-source Intrusion Detection System (IDS)**, **Intrusion Prevention System (IPS)**, and **network monitoring tool** developed and maintained by the **community-run Open Information Security Foundation (OISF)**.

## Main Operational Modes of Suricata:

1. **Active Mode (IDS)**:
   - Suricata works in active mode as an **Intrusion Detection System (IDS)**. In this mode, it **monitors** network traffic, detecting threats and generating alerts without blocking or stopping the traffic.

2. **Passive Mode (IPS)**:
   - In passive mode, Suricata functions as an **Intrusion Prevention System (IPS)**, where it not only detects threats but also **takes preventive actions** like blocking malicious traffic to stop potential attacks in real-time.


**Installation**

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

**Removing Suricata**

```bash
sudo apt-get remove suricata
```

For further information on Suricata and its setup, you can visit the official OISF Launchpad.


# Suricata Alert Rule Creation and Configuration

### Rule Format

The basic structure of a Suricata alert rule is:

alert <protocol> <source_ip> <source_port> -> <destination_ip> <destination_port> (msg:"<message>"; sid:<unique_id>; rev:<revision_number>; <additional_options>)

css


### Example Rule

```plaintext
alert http any any -> any any (msg:"Potential malicious HTTP request"; content:"malicious-pattern"; http_uri; sid:100001; rev:1;)

Steps to Write the Rule

    Protocol: Specify the protocol (e.g., http, tcp).
    Source IP/Port: Define the source IP/port (use any for all).
    Destination IP/Port: Define the destination IP/port (use any for all).
    Message: Descriptive alert message.
    SID: Unique identifier (greater than 100,000).
    Revision: Rule version number.
    Additional Options: Add any needed options (e.g., content, http_uri).

Save the Rule

Save the rule in a file with a .rules extension (e.g., custom.rules).
Configuring Suricata to Use the Rule
Edit the Configuration File

    Open Suricata's configuration file:

    bash

sudo nano /etc/suricata/suricata.yaml

Add your custom rule file in the rule-files section:

yaml

    rule-files:
      - /etc/suricata/rules/custom.rules

Reload Suricata

Restart Suricata to apply the new rules:

bash

sudo systemctl restart suricata

Verify the Rule

Check logs at /var/log/suricata/suricata.log to confirm the rule is loaded.
Test the Rule

Generate matching traffic to test:

bash

curl http://your-target-url/malicious-pattern

Check the logs for alerts.


