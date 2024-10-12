# Sigma CLI

Use sigma CLI effectively, create detection rules, and convert them into formats compatible with various backends like Splunk,Elk,and etc. sigmahq.io

Useful Tools for Generating Sigma Rules

To make Sigma rule creation faster and easier, you can use the following tools:
- SIGMA Rule Converter

A user-friendly tool that helps you convert different query formats (such as SPL, KQL, etc.) into Sigma rules quickly. Great for speeding up the rule generation process.
- UUID Generator

This tool generates unique IDs (UUIDs) for your Sigma rules, ensuring that each rule is identifiable and trackable.
- Uncoder.io

An online platform to convert detections from various SIEM tools into Sigma rules. This is part of the official Sigma GitHub project and simplifies writing detections for multiple platforms.

## Installation

To get started with Sigma CLI, follow these steps:

- **Clone the Sigma CLI repository:**
```bash
   git clone https://github.com/SigmaHQ/sigma-cli.git
   cd sigma-cli
   poetry install && poetry shell
   sigma --version
 ```
   
- **install dependencies using Poetry:**

```bash
poetry install && poetry shell
```
- **Verify the installation:**
 ```bash
sigma --version
  ```
Example output:
```bash
sigma plugin list

| Identifier           | Type     | State   | Description                                                  | Compatible? |
+----------------------+----------+---------+--------------------------------------------------------------+-------------+
| splunk               | backend  | stable  | Splunk backend for conversion into SPL ...                   | yes         |
...

```

- Get list of plugins
``` bash
| Identifier     | Type    | State  | Description               | Compatible? |
|----------------|---------|--------|---------------------------|-------------|
| ibm-qradar-aql | backend | stable | IBM QRadar AQL queries    | no          |
| cortexxdr      | backend | stable | Cortex XDR XQL queries    | yes         |
| carbonblack    | backend | stable | Carbon Black EDR queries  | yes         |
...
```
## Configuration

Here’s how to properly configure a Sigma rule with an example for detecting when an Okta user account is locked out. Follow these steps:



```yaml

title: Okta User Account Locked Out
id: 14701da0-4b0f-4ee6-9c95-2ffb4e73bb9a
status: test
description: Detects when a user account is locked out.
```
Title and Metadata

   Title: A short, descriptive name for the rule, explaining what it detects.
    ID: A unique identifier (UUID format) used for easy reference and tracking of the rule.
    Status: Indicates whether the rule is in a "test" phase or "production" (ready for use).
    Description: A brief explanation of what the rule detects.

```yaml
references:
    - https://developer.okta.com/docs/reference/api/system-log/
    - https://developer.okta.com/docs/reference/api/event-types/
```
References
 References: Links to relevant documentation or sources, providing background for the detection logic. These can help you understand where the rule’s logic comes from or point to official sources for further reading.

```yaml
author: Austin Songer @austinsonger
date: 2021-09-12
modified: 2022-10-09
```
Author and Date

   Author: The creator of the rule, useful for attribution or collaboration.
    Date: The date the rule was created.
    Modified: The date the rule was last updated to track changes.

```yaml
tags:
    - attack.impact
```

Tags
 Tags: Keywords that help categorize the rule. Tags can describe the type of attack or technique the rule is targeting (e.g., "attack.impact"). These tags make the rule easier to search and organize.

```yaml
logsource:
    product: okta
    service: okta
```

Log Source
  Logsource: Specifies where the log data comes from (e.g., Okta or another service). This tells the Sigma rule engine which logs to look at to trigger the detection.

``` yaml
detection:
    selection:
        displaymessage: Max sign in attempts exceeded
    condition: selection
```

Detection Logic
 Selection: Defines the specific event or fields in the logs that the rule should look for. This is where you specify the key data points (e.g., a specific error message or event type).
 Condition: The logic that applies to the selection. If the selection criteria are met, the rule triggers an alert.

``` yaml
falsepositives:
    - Unknown
```
False Positives
 False Positives: Scenarios where the rule may incorrectly trigger, causing a false alarm. Listing these helps avoid unnecessary alerts and gives insight into when the  rule may trigger incorrectly.

``` yaml

level: medium
```

Alert Level
 Level: The severity of the alert, which can be low, medium, or high. A "medium" level means the alert requires attention but is not immediately critical, while a "high" level indicates a more urgent situation
    
**Components:**
   - Detection: What malicious behaviour the rule searching for.
   - Logsource: What types of logs this detection should search over.
   - Metadata:  Other information about the detection.

``` yaml 
    detection: 
     selection:
        displaymessage: Max sign in attempts exceeded
    condition: selection
```
