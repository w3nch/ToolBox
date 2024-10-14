# Security Operations Center (SOC) Overview
## What is a SOC?

A Security Operations Center (SOC) is a team of security professionals working to monitor, detect, analyze, and mitigate security threats 24/7, 365 days a year. There are three types of SOCs:

    In-house SOC: Managed internally by an organization's staff.
    Outsourced SOC: Managed by a third-party provider.
    Hybrid SOC: A combination of in-house and outsourced services.

SOCs follow structured methodologies and playbooks to ensure continuous threat management and security.
Key Functions of a SOC

## The SOC operates in a continuous cycle of:

    Monitor - Real-time threat monitoring.
    Detect - Identification of security incidents.
    Respond - Taking action to mitigate and address security threats.

## These actions are supported by the following pillars:

    People: The skilled security professionals in the SOC.
    Processes: Standard procedures and playbooks for handling incidents.
    Technology: Security tools and systems used for monitoring, detection, and response.

## SOC Roles

    Security Analysts (SOC L1):
        Initial monitoring and triage.
        Determine whether alerts are true positives or false negatives.
        Escalate incidents to higher levels.

    Senior Security Analysts (SOC L2):
        Deeper investigation of incidents.
        Handle escalations from L1 and provide advanced analysis.

    Incident Responders (SOC L3):
        Lead incident response efforts.
        Perform root cause analysis and remediation.

    Threat Hunter:
        Proactively search for potential threats.
        Analyze attacker behaviours and tools.

    Threat Intelligence Analyst:
        Analyze threat intelligence data to understand trends.
        Provide actionable insights to the team.

    Security Engineer:
        Design and implement security systems.
        Manage tools like firewalls, SIEM, and other security platforms.

    SOC Manager:
        Oversee day-to-day operations and ensure processes are being followed.
        Implement effective security measures.

## Tools Used in a SOC

A SOC uses various security tools, such as:

    SIEM (Security Information and Event Management):
    Collects, analyzes, and correlates security event data.

    SOAR (Security Orchestration, Automation, and Response):
    Automates responses to security incidents.

    EDR (Endpoint Detection and Response):
    Monitors and responds to threats at the endpoint level.

    WAF (Web Application Firewall):
    Protects web applications from attacks.

    IDS/IPS (Intrusion Detection/Prevention Systems):
    Detects and prevents malicious network activities.

## Daily Life of a SOC L1 Analyst

    Monitor security alerts and logs.
    Triage to determine if alerts are real threats (true positives) or false alarms (false negatives).
    Escalate issues to L2/L3 if necessary.
    Recommend resolutions or improvements based on findings.

## Common Threats

1. **Social Engineering**  
   Social engineering involves manipulating individuals into divulging confidential or personal information that can be used for fraudulent purposes. Attackers exploit psychological factors to trick victims into making security mistakes.
   - **Phishing**: A method where attackers send fraudulent emails pretending to be from reputable sources to steal personal information, such as login credentials or credit card numbers.
   - **Quishing**: A variant of phishing that uses QR codes to direct victims to malicious sites or to install malware.
   - **Vishing**: Voice phishing, where attackers use phone calls to trick individuals into providing sensitive information, often posing as legitimate entities such as banks or government agencies.
   - **Whaling**: A highly targeted phishing attack directed at senior executives or important figures within an organization to gain access to sensitive corporate information.

2. **Identity Compromise**  
   Identity compromise refers to unauthorized access to personal accounts or systems with the intent to carry out malicious activities, such as data theft or fraud.
   - **Credential Dumps**: Collections of usernames and passwords stolen from data breaches that attackers use to gain access to various accounts.
   - **Brute Force Attacks**: Automated methods used to guess passwords by trying numerous combinations until the correct one is found, often facilitated by powerful computing resources.
   - **Social Engineering**: Utilizing manipulation tactics to persuade individuals to disclose their login information or security questions that can be exploited.

3. **Malware**  
   Malware (malicious software) is designed to disrupt, damage, or gain unauthorized access to computer systems and networks. It is often used for financial gain or to cause harm.
   - **Worm**: A type of malware that replicates itself to spread to other computers without needing a host file.
   - **Spyware**: Software that secretly monitors user activity and collects information without the user’s knowledge, often used for identity theft.
   - **Adware**: Software that displays unwanted advertisements on the user’s device, often bundled with free software, and may track user behavior.
   - **Ransomware**: A form of malware that encrypts the victim's data, rendering it inaccessible, and demands payment (usually in cryptocurrency) for the decryption key.
   - **Trojan**: Malware disguised as legitimate software that, once installed, can create backdoors for attackers to gain access to the system.
   - **Fileless Malware**: A sophisticated type of malware that operates in-memory, making it difficult to detect as it does not leave traditional file-based footprints.

4. **Vulnerable Software**  
   This refers to applications or systems that have known security flaws or vulnerabilities due to outdated software or insufficient security controls. Attackers can exploit these vulnerabilities to gain unauthorized access or control over systems.
   - Regular updates and patch management are crucial to mitigate risks associated with vulnerable software.

5. **Sensitive Data Exposure**  
   Sensitive data exposure occurs when sensitive information is improperly protected, leading to unauthorized access. This can result from poor encryption practices, misconfigured databases, or insecure data transmission methods.
   - Organizations must implement strong data protection measures, including encryption and secure access controls, to safeguard sensitive information.

6. **Supply Chain Compromise**  
   Supply chain compromise involves attacks that target the vulnerabilities in the supply chain of products or services. Attackers may infiltrate third-party vendors or software updates to gain access to larger organizations.
   - This can lead to significant data breaches or system compromises, highlighting the importance of securing the entire supply chain.

Understanding these common threats is crucial for developing effective security measures and strategies to protect against potential attacks. Regular training and awareness programs can help individuals and organizations remain vigilant against these evolving threats.

## What is a SIEM?

**SIEM** (Security Information and Event Management) is a comprehensive solution that provides real-time analysis of security alerts generated by various hardware and software infrastructures in an organization. It plays a critical role in modern cybersecurity strategies by centralizing and correlating security-related data for effective threat detection and response.

### Key Components of SIEM

1. **Log Management**  
   Collecting, storing, and managing log data from various sources to ensure that critical security information is readily available for analysis and compliance.

2. **Correlation and Analytics**  
   Analyzing and correlating log data to identify patterns and detect anomalies that may indicate potential security threats. This process involves the use of predefined rules and heuristics to correlate events and alerts.

3. **Ticketing and Reporting**  
   Integrating with ticketing systems to facilitate incident response and management. SIEM solutions provide reporting capabilities to generate insights and compliance reports.

4. **Centralized Data Management**  
   Centralizing data from multiple sources allows security teams to have a unified view of the organization's security posture. This centralization aids in the effective management of alerts and case management.

## Popular SIEM Solutions

- **[Security Onion](https://securityonionsolutions.com/)**  
  A free and open-source Linux distribution for intrusion detection, network security monitoring, and log management. It includes a variety of tools to help detect and respond to security threats.

- **Splunk**  
  A powerful platform for searching, monitoring, and analyzing machine-generated data in real-time. Splunk provides advanced analytics and visualization features, making it a popular choice among enterprises.

- **Wazuh**  
  An open-source security monitoring tool that provides intrusion detection, log analysis, and compliance monitoring. Wazuh is designed to help organizations identify security threats and vulnerabilities.

- **Elasticsearch**  
  A distributed, RESTful search and analytics engine that serves as a foundational component for many SIEM solutions. It allows for real-time search, analysis, and visualization of log data.


## Summary

The SOC's main goal is to protect the Confidentiality, Integrity, and Availability of an organization's data and systems, ensuring a secure and stable environment.
Learn More:

    T-Pot Honeypot - A multi-honeypot platform for collecting threat data.
    TheHive Project - An incident response platform for security analysts
