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

Get list of plugins
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




