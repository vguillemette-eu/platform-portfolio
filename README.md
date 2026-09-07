# Platform Portfolio

Infrastructure as Code & Kubernetes Multi-Cloud Portfolio.

## Repository Structure

```text
.
├── ansible/
│   ├── inventory/
│   │   └── hosts.yml
│   ├── playbooks/
│   │   ├── sysreq.yml
│   │   └── tailscale.yml
│   └── site.yml
├── .gitignore
└── requirements.txt
```

## Quickstart

### 1. Environment Setup

Activate the Python virtual environment and install dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt
```

### 2. Infrastructure Provisioning

Run the master playbook to configure system requirements and Tailscale mesh:

```bash
export TAILSCALE_AUTHKEY="tskey-auth-xxxxxx"
ansible-playbook -i ansible/inventory ansible/site.yml
```
