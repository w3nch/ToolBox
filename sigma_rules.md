# 🧠 Daily Learning Guide for Sigma CLI

Welcome to the **Daily Learning Guide**! This repository is designed to help you understand how to use Sigma CLI effectively, create detection rules, and convert them into formats compatible with various backends like Splunk,Elk,and etc.

## 🚀 Installation

To get started with Sigma CLI, follow these steps:

- **Clone the Sigma CLI repository:**
   ```bash
   git clone https://github.com/SigmaHQ/sigma-cli.git
   cd sigma-cli
   poetry install && poetry shell
   sigma --version ```
   
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
