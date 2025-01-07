# IDA LAW - ISO Certifications

## Purpose of the Repository

This repository, hosted at IDA-LAW/iso-certifications, serves as the central hub for documenting and maintaining the policies, processes, and compliance measures required for IDA Law to achieve and sustain ISO certifications. The repository ensures transparency, accountability, and ease of collaboration in implementing best practices aligned with the following ISO standards:
- ISO/IEC 27001: Information Security Management System
- ISO 22301: Business Continuity Management System
- ISO 9001: Quality Management System
- ISO/IEC 27701: Privacy Information Management System
- ISO/IEC 27017: Information Security for Cloud Services
- ISO/IEC 27018: Protection of PII in Public Clouds
- ISO 45001: Occupational Health and Safety Management
- ISO 14001: Environmental Management

### Core Objectives
1. **Documentation of Compliance Measures**
  - Provide structured and version-controlled policies, procedures, and templates for each ISO certification.
2. **Continuous Improvement**
  - Establish workflows and automation to ensure periodic review, updates, and alignment with the latest ISO standards.
3. **Centralized Collaboration**
  - Act as the single source of truth for all stakeholders, including legal, IT, compliance, and external auditors, ensuring seamless coordination.

### Repository Components
- **Policies and Procedures:** Detailed documentation tailored to IDA Law’s operations.
- **Implementation Steps:** A step-by-step guide for achieving and maintaining compliance with each standard.
- **Audit Readiness:** Checklists and reports to facilitate internal and external audits.
- **Automation Tools:** Scripts and workflows to automate document validation, versioning, and report generation.

### Processes Covered
- Information security management, including access controls, encryption, and incident response.
- Business continuity planning, including disaster recovery and redundancy measures.
- Quality assurance for legal and IT services.
- Protection and management of personal data across cloud and local environments.
- Health, safety, and environmental responsibility within operations.

### Commitment to Compliance
IDA Law is committed to maintaining the highest standards of quality, security, and sustainability. This repository is a reflection of that commitment, ensuring that all processes are documented, monitored, and improved continuously.

![ISO Certifications](https://img.icons8.com/ios-filled/50/000000/certification.png)

## Running the example

- Open this example in VS Code
- `pnpm install`
- `pnpm run compile`
- `F5` to start debugging

## Offices for IDA Law

### Johannesburg Office:
![Johannesburg Icon](https://img.icons8.com/ios-filled/50/000000/johannesburg.png)  
30 Beyers Naude Drive, Service Road, Franklin Roosevelt Park, Johannesburg, 2195  
T: 011 837 0366 | F: 011 837 0716  
legal@idalaw.co.za

### Boksburg Office:
![Boksburg Icon](https://img.icons8.com/ios-filled/50/000000/boksburg.png)  
77 Rietfontein Road,  
Boksburg, 1459  
T: 010 035 0915 | F: 086 694 1726  
collections@idalaw.co.za

### Cape Town Office:
![Cape Town Icon](https://img.icons8.com/ios-filled/50/000000/cape-town.png)  
Millenium Business Park, 19 Edison Way, Unit 162 Century City, Cape Town, 7140  
T: 021 202 3418  
law@idalaw.co.za

## Enhanced VS Code Setup

To supercharge your VS Code environment for the iso-certifications project, here’s a comprehensive setup including additional tooling, automation, and enhancements to streamline workflows:

### Enhanced .vscode Directory Structure

Extend the .vscode folder with these configurations:

```
.vscode/
├── extensions.json
├── settings.json
├── tasks.json
├── launch.json
├── markdownlint.json
├── snippets/
│   └── iso-docs.code-snippets
├── workspace.code-workspace
└── build/
    └── build-docs.sh
```

### Updated and Optimized Configuration Files

1. **extensions.json**

Encourage all collaborators to install the necessary extensions.

```json
{
  "recommendations": [
    "davidanson.vscode-markdownlint",
    "yzhang.markdown-all-in-one",
    "streetsidesoftware.code-spell-checker",
    "github.vscode-pull-request-github",
    "eamodio.gitlens",
    "editorconfig.editorconfig",
    "esbenp.prettier-vscode",
    "bierner.markdown-preview-github-styles",
    "redhat.vscode-yaml",
    "ms-azuretools.vscode-docker",
    "hashicorp.terraform",
    "ms-vscode.live-server"
  ]
}
```

2. **settings.json**

Optimize the workspace settings for consistent formatting and productivity.

```json
{
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.wordWrap": "on",
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "files.autoSave": "onFocusChange",
  "files.eol": "\n",
  "markdownlint.config": {
    "MD013": { "line_length": 120 },
    "MD041": false,
    "MD033": false
  },
  "yaml.schemas": {
    "https://json.schemastore.org/github-workflow.json": ".github/workflows/*.yml"
  },
  "docker.languageserver.formatter": "prettier",
  "liveServer.settings.port": 5500,
  "cSpell.words": [
    "ISO",
    "IDA",
    "Johannesburg",
    "Boksburg",
    "Edison",
    "Franklin"
  ]
}
```

3. **tasks.json**

Add tasks for automating common actions like linting, spell-checking, and building documents.

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Build Documentation",
      "type": "shell",
      "command": "./.vscode/build/build-docs.sh",
      "group": "build",
      "problemMatcher": []
    },
    {
      "label": "Lint Markdown Files",
      "type": "shell",
      "command": "npx markdownlint '**/*.md' --fix",
      "problemMatcher": []
    },
    {
      "label": "Check Spelling",
      "type": "shell",
      "command": "npx cspell '**/*.md'",
      "problemMatcher": []
    },
    {
      "label": "Preview Markdown",
      "type": "shell",
      "command": "code --preview README.md",
      "problemMatcher": []
    }
  ]
}
```

4. **launch.json**

Configure debugging for build and linting scripts.

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Run Build Script",
      "program": "${workspaceFolder}/.vscode/build/build-docs.sh"
    }
  ]
}
```

5. **markdownlint.json**

Refine Markdown linting rules for ISO standards.

```json
{
  "MD013": { "line_length": 120 },
  "MD041": false,
  "MD033": false,
  "MD005": false,
  "MD007": { "indent": 2 }
}
```

6. **snippets/iso-docs.code-snippets**

Add reusable snippets for quickly writing ISO-compliant documentation.

```json
{
  "ISO Header": {
    "prefix": "iso-header",
    "body": [
      "# ${1:Policy Title}",
      "## Purpose",
      "${2:Purpose statement.}",
      "## Scope",
      "${3:Scope description.}",
      "## Responsibilities",
      "- ${4:Responsibility details.}",
      "## References",
      "- ${5:Reference links.}"
    ],
    "description": "Template for ISO policy header"
  }
}
```

7. **workspace.code-workspace**

Configure a multi-root workspace for better organization.

```json
{
  "folders": [
    {
      "path": "."
    },
    {
      "path": "../related-repo"
    }
  ],
  "settings": {
    "files.exclude": {
      "**/.vscode": false
    }
  }
}
```

8. **build/build-docs.sh**

Automate the process of building, linting, and previewing Markdown files.

```bash
#!/bin/bash

echo "Building ISO Certification Documents..."
npx markdownlint "**/*.md" --fix
echo "Linting Complete."

echo "Generating PDF Previews..."
for file in $(find . -name "*.md"); do
  markdown-pdf $file
done

echo "Build Complete. All documentation is ready!"
```

### Key Extensions

Install these additional extensions for enhanced functionality:
1. Live Server (ritwickdey.liveserver): Preview documentation changes in real-time.
2. Docker (ms-azuretools.vscode-docker): Manage Docker configurations for hosting ISO services.
3. Terraform (hashicorp.terraform): If infrastructure-as-code (IaC) is needed for deployment.

### Automation Enhancements
1. GitHub Actions: Add workflows in .github/workflows to validate documents and deploy them.
2. CI/CD Integration: Use Azure Pipelines or GitHub Actions to automate linting and spell-checking.
3. Pre-Commit Hooks: Use husky to enforce linting and spell-checking before commits.

### Final Steps
1. Save all the .vscode files in your project.
2. Run `pnpm install markdownlint-cli cspell markdown-pdf` to install necessary tools locally.
3. Test the setup by running tasks via `Ctrl+Shift+P → Tasks: Run Task`.

This setup will streamline workflows, enforce consistency, and make your project easy to maintain and collaborate on!

## Technology

As a professional firm, we only use the latest state-of-the-art hardware. Our software is regularly kept up to date by our in-house IT Department, which is supported by an outsourced IT Firm.

### IT Infrastructure
- **Uninterrupted Internet and Email:** Guaranteed by ADSL lines together with backup.
- **24/7 Server Operations:** Our servers run back-to-back 24 hours a day with an A-Grade firewall.
- **Off-Site Backups:** Backups are stored off-site and are done on a daily basis.
- **Uninterrupted Power Supply:** Ensured to maintain continuous operations.

### Software Utilized
- **Legal Software:** Legalsuite, Microsoft Office, Winded, Butterworths, Deedsearch, LexisNexis
