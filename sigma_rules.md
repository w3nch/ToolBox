# 🧠 Daily Learning Guide for Sigma CLI

Welcome to the **Daily Learning Guide**! This repository is designed to help you understand how to use Sigma CLI effectively, create detection rules, and convert them into formats compatible with various backends like Splunk,Elk,and etc. sigmahq.io

## 🚀 Installation

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
+----------------------+----------+---------+--------------------------------------------------------------+-------------+
| Identifier           | Type     | State   | Description                                                  | Compatible? |
+----------------------+----------+---------+--------------------------------------------------------------+-------------+
| splunk               | backend  | stable  | Splunk backend for conversion into SPL ...                   | yes         |
...
+----------------------+----------+---------+--------------------------------------------------------------+-------------+
```

- Get list of plugins
``` bash
sigma plugin list --plugin-type backend
+----------------------+---------+---------+--------------------------------------------------------------+-------------+--------------+
| Identifier           | Type    | State   | Description                                                  | Compatible? | Capabilities |
+----------------------+---------+---------+--------------------------------------------------------------+-------------+--------------+
| ibm-qradar-aql       | backend | stable  | IBM QRadar backend for conversion into AQL queries. Contains | no          | 0            |
|                      |         |         | mappings for fields and logsources                           |             |              |
| cortexxdr            | backend | stable  | Cortex XDR backend that generates XQL queries.               | yes         | 0            |
| carbonblack          | backend | stable  | Carbon Black backend that supports queries for both          | yes         | 0            |
|                      |         |         | Enterprise EDR (fka Threat Hunter) and EDR (fka Response)    |             |              |
| sentinelone          | backend | stable  | SentinelOne backend that generates Deep Visibility queries.  | yes         | 0            |
| sentinelone-pq       | backend | stable  | SentinelOne backend that generates PowerQuery queries.       | yes         | 0            |
| splunk               | backend | stable  | Splunk backend for conversion into SPL and tstats data model | yes         | 3            |
|                      |         |         | queries as plain queries and savedsearches.conf              |             |              |
| insightidr           | backend | stable  | Rapid7 InsightIDR backend that generates LEQL queries.       | no          | 0            |
| qradar               | backend | stable  | IBM QRadar backend for conversion into AQL and extension     | no          | 0            |
|                      |         |         | packages.                                                    |             |              |
| elasticsearch        | backend | stable  | Elasticsearch backend converting into Lucene, ES|QL (with    | yes         | 3            |
|                      |         |         | correlations) and EQL queries, plain, embedded into DSL or   |             |              |
|                      |         |         | as Kibana NDJSON.                                            |             |              |
| opensearch           | backend | stable  | Opensearch backend converting into Lucene queries and        | no          | 0            |
|                      |         |         | Opensearch alerting rules.                                   |             |              |
| ala-socprime         | backend | devel   | Azure Log Analytics backend with Windows log support         | no          | 0            |
|                      |         |         | maintained by SOC Prime.                                     |             |              |
| stix                 | backend | devel   | STIX backend converting into plain STIX queries. Contains    | no          | 0            |
|                      |         |         | mappings for STIX 2.0 and STIX Shifter taxonomies.           |             |              |
| loki                 | backend | stable  | Loki backend for conversion into Loki LogQL queries (plain   | no          | 2            |
|                      |         |         | and ruler YAML for alerts) and pipelines with mappings for   |             |              |
|                      |         |         | Grafana and promtail Sysmon data.                            |             |              |
| crowdstrike          | backend | stable  | CrowdStrike Logscale backend and pipelines for CrowdStrike   | no          | 0            |
|                      |         |         | Falcon platform and Falcon Data Replicator (FDR) logs.       |             |              |
| powershell           | backend | testing | PowerShell backend converting into PowerShell queries.       | no          | 0            |
| microsoft365defender | backend | stable  | Microsoft 365 Defender (formally mdatp) backend and pipeline | yes         | 0            |
|                      |         |         | for conversion of log sources with Sysmon field schema to    |             |              |
|                      |         |         | Microsoft Advanced Hunting Queries in Kusto Query Language   |             |              |
|                      |         |         | (KQL)                                                        |             |              |
| hawk                 | backend | testing | HAWK.io MDR backend and pipeline for conversion of log       | no          | 0            |
|                      |         |         | sources to HAWK.io BETree queries.                           |             |              |
| datadog              | backend | testing | Datadog Cloud SIEM backend and pipeline for conversion of    | no          | 0            |
|                      |         |         | log sources to Datadog Query Syntax                          |             |              |
| dictquery            | backend | stable  | DictQuery backend to convert sigma to dictquery query        | no          | 0            |
|                      |         |         | strings                                                      |             |              |
| sqlite               | backend | testing | SQLite and Zircolite backend                                 | yes         | 0            |
| uberagent            | backend | stable  | uberAgent backend                                            | yes         | 0            |
| panther              | backend | devel   | Panther sdyaml backend                                       | yes         | 0            |
| trellix_helix        | backend | devel   | Trellix Helix Backend                                        | yes         | 0            |
| quickwit             | backend | devel   | Quickwit Backend                                             | yes         | 0            |
| netwitness           | backend | testing | NetWitness Backend that generates application rules          | yes         | 0            |
| logpoint             | backend | stable  | Logpoint Pysigma Backend                                     | no          | 0            |
+----------------------+---------+---------+--------------------------------------------------------------+-------------+--------------+
```
## 🔧 Proper Configuration of Sigma Rules

Here’s how to properly configure a Sigma rule with an example for detecting when an Okta user account is locked out. Follow these steps:



```yaml
title: Okta User Account Locked Out
id: 14701da0-4b0f-4ee6-9c95-2ffb4e73bb9a
status: test
description: Detects when a user account is locked out.
references:
    - https://developer.okta.com/docs/reference/api/system-log/
    - https://developer.okta.com/docs/reference/api/event-types/
author: Austin Songer @austinsonger
date: 2021-09-12
modified: 2022-10-09
tags:
    - attack.impact
logsource:
    product: okta
    service: okta
detection:
    selection:
        displaymessage: Max sign in attempts exceeded
    condition: selection
falsepositives:
    - Unknown
level: medium
```
1. Title and Metadata

    Title: A short, descriptive name for the rule, explaining what it detects.
    ID: A unique identifier (UUID format) used for easy reference and tracking of the rule.
    Status: Indicates whether the rule is in a "test" phase or "production" (ready for use).
    Description: A brief explanation of what the rule detects.

2. References

    References: Links to relevant documentation or sources, providing background for the detection logic. These can help you understand where the rule’s logic comes from or point to official sources for further reading.

3. Author and Date

    Author: The creator of the rule, useful for attribution or collaboration.
    Date: The date the rule was created.
    Modified: The date the rule was last updated to track changes.

4. Tags

    Tags: Keywords that help categorize the rule. Tags can describe the type of attack or technique the rule is targeting (e.g., "attack.impact"). These tags make the rule easier to search and organize.

5. Log Source

    Logsource: Specifies where the log data comes from (e.g., Okta or another service). This tells the Sigma rule engine which logs to look at to trigger the detection.

6. Detection Logic

    Selection: Defines the specific event or fields in the logs that the rule should look for. This is where you specify the key data points (e.g., a specific error message or event type).
    Condition: The logic that applies to the selection. If the selection criteria are met, the rule triggers an alert.

7. False Positives

    False Positives: Scenarios where the rule may incorrectly trigger, causing a false alarm. Listing these helps avoid unnecessary alerts and gives insight into when the rule may trigger incorrectly.

8. Alert Level

    Level: The severity of the alert, which can be low, medium, or high. A "medium" level means the alert requires attention but is not immediately critical, while a "high" level indicates a more urgent situation.
