# Architecture Documentation for the RO Wallet

This documentation provides insight into the architecture of the RO Wallet, describing the scope, functions, involved entities and components, detailed data flows, cryptography and more.

This document does not include any code or developer documentation, which will be released at a later stage.

## Current Status

The project team currently focuses on the design and the implementation of the PID function (Online Issuance and Presentation) and the respective Wallet Core functions (such as wallet instance revocation). Further functions, like EAAs or QES, will be added in later stages.

## Links

- The GitHub repository for this document is [hosted on GitHub](https://github.com/Ministerul-Afacerilor-Interne/rowallet-documentation).
- For reading, the content is available at [this website](https://ministerul-afacerilor-interne.github.io/rowallet-documentation/).

## Local Development & Building

### Prerequisites

- Python 3.11+ (or Docker)
- Git

### Option 1: Python Virtual Environment

1. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/macOS
   # or: .\venv\Scripts\Activate.ps1  # Windows PowerShell
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Start the live-reloading preview server:
   ```bash
   mkdocs serve
   ```
   Open `http://localhost:8000` in your browser.

4. Validate the site with strict checking (zero warnings/errors):
   ```bash
   mkdocs build --strict
   ```

### Option 2: Docker & Docker Compose

Run the containerized preview server with automatic live-reloading:

```bash
docker compose up
```

Open `http://localhost:8000` in your browser.

### Option 3: Ansible Automation (Optional)

For automated workstation setup or self-hosted staging deployments:

```bash
cd ansible
ansible-playbook -i inventory.ini playbook.yml
```

## CI/CD Pipeline

- **Continuous Integration (`.github/workflows/ci.yml`)**: Automatically validates documentation and executes `mkdocs build --strict` on pull requests and pushes to ensure no broken links, malformed admonitions, or syntax errors are merged.
- **Continuous Deployment (`.github/workflows/pages.yml`)**: Deploys the built documentation to GitHub Pages upon pushing to `main`.

## Providing Feedback

To provide feedback, please contact us by e-mail at feedback.rowalletdocumentation@mai.gov.ro.
