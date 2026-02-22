🇪🇺 EU AI ACT SIEM COMPLIANCE DETECTIONS 🤖

📝 Overview

EU AI Act SIEM Compliance Detections is a specialized open-source repository providing production-ready Security Information and Event Management (SIEM) detection rules, Splunk SPL queries, and SOC incident response playbooks. 🛡️

This project serves as a technical bridge between regulatory requirements and security operations. It provides concrete detective controls to help organizations demonstrate compliance with the EU AI Act (Regulation (EU) 2024/1689), focusing specifically on High-Risk AI Systems and General-Purpose AI (GPAI) monitoring.

📂 Repository Structure 🏗️

To ensure proper rendering, the project follows this strict directory hierarchy:

<img width="1119" height="348" alt="image" src="https://github.com/user-attachments/assets/b295f5cd-c3d3-4e7d-86e0-d7896943409e" />



⚠️ The Problem

Legal frameworks define what must be done, but they rarely explain how to monitor it in a production SIEM like Splunk. For SOC teams, the EU AI Act introduces new threat vectors that traditional EDR/Network tools miss:

• Prompt Injections: Bypassing safety filters to extract secrets. 💉


• Data Poisoning: Tampering with training sets to bias model outputs. 🧪


• Human Oversight Bypass: AI agents acting without a human "kill-switch." 🚫👤

Failure to detect these events leads to regulatory non-compliance and massive fines (up to 35M EUR or 7% of global turnover). 💸

🚀 The Solution

This repository translates abstract legal articles into deployable SIEM logic. By implementing these detections, you can:


• ✅ Automate Compliance: Monitor Article 10, 14, and 15 requirements in real-time.


• ✅ Enhance Visibility: Use MITRE ATLAS and OWASP LLM mappings to explain "Technical Risk" to "Legal Risk."


• ✅ Standardize Response: Use pre-built playbooks to ensure SOC analysts handle AI incidents correctly.


• 📊 Regulatory & Threat Framework Mapping Table

<img width="1155" height="472" alt="image" src="https://github.com/user-attachments/assets/4ef25635-2f5b-413e-a9f0-31362fed0c98" />


⚖️ Regulatory Deep Dive: Articles & Violation Prevention 🏛️

This repository helps organizations avoid "Failure to Monitor" violations by providing technical evidence for the following articles:

🛡️ Article 10: Data and Data Governance


• The Law: Requires high-risk AI systems to use high-quality training, validation, and testing datasets that are subject to appropriate governance.


• Violation Prevention: We provide logic to detect unauthorized tampering or "poisoning" of training datasets. It flags anomalous access to data lakes containing AI training data, preventing compromised model integrity.

👤 Article 14: Human Oversight


• The Law: High-risk AI must be designed to allow natural persons to oversee the system to prevent or minimize risks (Automation Bias).


• Violation Prevention: Triggers alerts when an AI agent executes a "critical action" (e.g., financial transfer, data deletion) without a corresponding human approval token in the logs.

⚡ Article 15: Accuracy, Robustness, and Cybersecurity


• The Law: Systems must be resilient against attempts by third parties to alter their use, behavior, or performance by exploiting vulnerabilities.


• Violation Prevention: This is our primary focus. We provide SPL queries to detect Prompt Injection, Jailbreaking attempts, and Model Inversion attacks in real-time at the API Gateway level.

🛠️ Implementation Guide (Splunk)

1. Ingest Telemetry: Ensure your AI stack logs are mapped to the Splunk CIM. 🔌

2. Deploy Detections: Import the SPL queries from /detections/splunk/ as Correlation Searches. 🔍

3. Tune Thresholds: Use the baseline_builder.spl to establish "normal" AI behavior. ⚖️

Automate: Link Notable Events to SOAR playbooks in the /playbooks/ folder. ⚡

⚖️ Disclaimer

This repository provides technical security controls. Implementation does not constitute legal advice. While these detections serve as detective controls for the EU AI Act, organizations must consult with qualified legal counsel and ISO 42001 auditors to ensure full regulatory alignment. 🛑

🤝 Contributing

We welcome contributions! Please ensure any new PR includes:

• Relevant Article from the EU AI Act. 📜

• MITRE ATLAS Tactic/Technique mapping. 🗺️

• OWASP LLM Vulnerability category. 🔥

📄 License

Distributed under the MIT License. See LICENSE for more information. 📄

Maintained by Abhishek G Sharma, email id: contact@move78int.com 
