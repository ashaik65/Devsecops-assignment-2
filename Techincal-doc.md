🛡️ GitHub Advanced Security (GHAS) Integration – Technical Documentation
📌 1. Context – Why Are We Doing This?
Security is a foundational requirement for modern software development. As part of a DevSecOps strategy, enabling GitHub Advanced Security (GHAS) helps to identify and mitigate security vulnerabilities early in the development lifecycle.

This POC demonstrates integrating GHAS into a vulnerable sample Python project (damn-vulnerable-MCP-server) with the following security goals:

Code Scanning using GitHub’s CodeQL
Dependency Scanning with Dependabot
Secret Detection (e.g., AWS credentials)
Centralized visibility through Security Alerts
🔬 2. Thought Process (POC Details)
🔧 Tooling Selected:
CodeQL: Static code analysis engine that automatically finds vulnerabilities in Python code.
Dependabot: Dependency graph scanner that detects vulnerable versions in requirements.txt and Docker images.
GitHub Secret Scanning: Flags hardcoded credentials like AWS access keys, passwords, tokens.
🧪 Repository Setup:
Created GitHub repository.
Pushed intentionally vulnerable Python app (damn-vulnerable-MCP-server).
Added .github/workflows/codeql.yml for automatic code scanning.
Added .github/dependabot.yml to scan:
Python packages via pip (daily)
Docker base image (daily)
🪪 Secret Detection Tested:
Pushed an AWS Access Key ID + Secret Key in a test commit.
GitHub immediately blocked the push and triggered a secret alert, proving secret detection was working.

📷 Screenshots Attached:
1.Dependabot alerts showing CVEs

![image](https://github.com/user-attachments/assets/83ab4a19-98ce-4cc1-a28c-3e58ceb2bf3d)


