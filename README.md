# Platform Portfolio

Infrastructure as Code & Kubernetes Multi-Cloud Portfolio.

## Repository Structure

```text
.
└── ansible/
```

## Quickstart

### 1. Environment Setup

Activate the Python virtual environment and install Python dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt
```

### 2. System Requirements

Run the bootstrap playbook to prepare nodes:

```bash
ansible-playbook -i ansible/inventory ansible/playbooks/k3s-sysreq.yml
```
