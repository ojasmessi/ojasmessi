<!-- ============================  HEADER  ============================ -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=0:000000,55:0d1117,100:003b2b&height=210&section=header&text=OJAS%20PATIL&fontSize=62&fontColor=00FF9C&fontAlignY=40&animation=fadeIn&desc=SOC%20Analyst%20%20%2F%2F%20%20Detection%20Engineering%20%20%2F%2F%20%20AI%20Security&descSize=18&descAlignY=66&descAlign=50" alt="Ojas Patil — SOC Analyst, Detection Engineering, AI Security"/>
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=18&duration=2800&pause=900&color=00FF9C&center=true&vCenter=true&width=820&lines=%24+whoami+%E2%86%92+Security+Operations+Analyst+%7C+MSc+Cyber+Security+%7C+CEH+v12;%24+hunt+--siem+sentinel%2Cwazuh%2Csplunk+--lang+kql%2Cspl+--mitre+attack;%24+triage+--edr+sentinelone%2Cvision-one+--sla+P1-P3+--escalate+T2;%24+redteam+--target+llm-agent+--owasp+LLM01-LLM10+--map+atlas;%24+echo+%24STATUS+%E2%86%92+Open+to+SOC+%2F+Detection+%2F+AI+Security+roles+%E2%80%94+Dublin" alt="Terminal intro"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/CEH-v12-00FF9C?style=flat-square&labelColor=0d1117" alt="CEH v12"/>
  <img src="https://img.shields.io/badge/MSc-Cyber_Security-00FF9C?style=flat-square&labelColor=0d1117" alt="MSc Cyber Security"/>
  <img src="https://img.shields.io/badge/Enterprise_SOC-Reliance_Jio_%7C_Sequretek-00FF9C?style=flat-square&labelColor=0d1117" alt="Enterprise SOC"/>
  <img src="https://img.shields.io/badge/MITRE-ATT%26CK_%7C_ATLAS-00FF9C?style=flat-square&labelColor=0d1117" alt="MITRE"/>
  <img src="https://img.shields.io/badge/OWASP-LLM_Top_10-00FF9C?style=flat-square&labelColor=0d1117" alt="OWASP LLM"/>
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1200&color=36BCF7&center=true&vCenter=true&width=720&lines=SOC+Analyst+%7C+Incident+Response+%7C+Threat+Hunting;Building+detections+in+KQL+%E2%80%A2+SPL+%E2%80%A2+Wazuh+rules;Red-teaming+and+monitoring+LLM+applications;MSc+Cyber+Security+%E2%80%94+National+College+of+Ireland" alt="Typing intro"/>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/YOUR-LINKEDIN-SLUG/"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:oja2001pat@gmail.com"><img src="https://img.shields.io/badge/Email-oja2001pat%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
  <a href="https://tryhackme.com/p/ojaspatil10"><img src="https://img.shields.io/badge/TryHackMe-ojaspatil10-212C42?style=for-the-badge&logo=tryhackme&logoColor=white" alt="TryHackMe"/></a>
  <img src="https://img.shields.io/badge/📍_Dublin,_Ireland-Open_to_work-2ea44f?style=for-the-badge" alt="Location"/>
</p>

---

## 👋 About Me

I'm a **Security Operations Analyst** with hands-on enterprise SOC experience at **Reliance Jio** and **Sequretek**, and an **MSc in Cyber Security** from the National College of Ireland.

I triage, investigate and respond to threats across SIEM, EDR and network telemetry — and I spend my lab time **building and tuning the detections** that make that work faster. Lately I've been applying SOC thinking to a new attack surface: **LLM applications** — attacking them, putting guardrails around them, and streaming their activity into a SIEM.

```yaml
whoami:
  role:        Security Operations / SOC Analyst
  focus:       [Alert Triage, Incident Response, Threat Hunting, Detection Engineering, AI Security]
  siem:        [Microsoft Sentinel, Wazuh, Splunk, IBM QRadar (basic)]
  edr_xdr:     [SentinelOne, Trend Micro Vision One, Microsoft Defender]
  query:       [KQL, SPL, SQL]
  automation:  [Python, PowerShell, Bash]
  frameworks:  [MITRE ATT&CK, MITRE ATLAS, OWASP Top 10 for LLMs]
  certs:       [CEH v12, CSCU]
  location:    Dublin, Ireland
  looking_for: SOC Analyst • Detection Engineering • AI Security roles
```

---

## 🚀 Featured Projects

### 🤖 [LLM-SOC — Attacking, Defending & Monitoring an AI Chatbot](https://github.com/ojasmessi/LLM-SOC)
A hands-on AI-security lab that brings SOC workflows to LLM apps. I built a deliberately vulnerable RAG + tool-using HR chatbot (Llama 3.2 via Ollama), attacked it, wrapped it in a 4-layer "AI firewall", and wired every interaction into **Wazuh** with detections mapped to **OWASP LLM Top 10** and **MITRE ATLAS**.

```mermaid
flowchart LR
    A[Attacker / User] --> B[Input guardrail]
    B --> C[RAG retrieval]
    C --> D[Doc sanitiser]
    D --> E[LLM - Llama 3.2]
    E --> F[Tool allow-list]
    F --> G[Output guardrail: PII + canary]
    G --> A
    G -. JSON logs .-> H[(Wazuh / Sentinel)]
    H --> I[Alerts + IR playbook]
```

| Result | Guardrails off | Guardrails on |
|---|---|---|
| Attack success rate | 22% (11/50) | **4% (2/50)** — 82% reduction |
| Data exfiltration via email tool | Repeated | **0** |
| Benign questions blocked (false positives) | 0/10 | **0/10** |

- Demonstrated **indirect prompt injection**: a hidden instruction inside a company FAQ made the agent email data externally.
- Caught a **tool-channel leak** the output filter missed — found through log review, fixed, and the baseline corrected from 12% → 22%.
- Wrote **8 Wazuh rules + KQL equivalents** and an **incident response playbook** (incl. GDPR 72-hour notification).

`Python` `FastAPI` `Ollama` `Garak` `Wazuh` `KQL` `OWASP LLM Top 10` `MITRE ATLAS`

---

### ☁️ Cloud SIEM & Incident Response Automation — Microsoft Sentinel (MSc Practicum)
Thesis: *Reducing Incident Response Time in Cybersecurity Operations.* Built an Azure SOC lab with Microsoft Sentinel and Log Analytics, then engineered detections and automated playbooks to shorten the alert-to-action path.

- **99.3% reduction in Mean Time to Detect** using custom KQL analytics rules.
- Automated triage playbooks: high-priority tagging, false-positive auto-closure, priority queueing.
- KQL workbooks visualising RDP brute-force activity, authentication anomalies and attacker geolocation.
- PowerShell pipeline for Windows event extraction and threat-intel / geo-IP enrichment; attack simulations mapped to MITRE ATT&CK.

`Microsoft Sentinel` `Azure Log Analytics` `KQL` `Logic Apps` `PowerShell` `MITRE ATT&CK`

---

### 🔐 [SSH Brute-Force Detection Lab — Splunk](https://github.com/ojasmessi/soc-analyst-portfolio/tree/main/project-01-ssh-brute-force)
Simulated SSH brute-force attacks (Hydra, Medusa) from Kali against Ubuntu, ingested `auth.log` into Splunk and wrote SPL detections for threshold-based failures and the **"many failures → one success"** compromise pattern. Delivered a multi-panel triage dashboard. Mapped to **T1110.001** and **T1548**.

`Splunk` `SPL` `Kali Linux` `Hydra` `Medusa` `Nmap`

---

### 🕵️ Reverse Shell Network Detection Lab — Wireshark
Simulated a Metasploit / Meterpreter C2 chain and identified encrypted command-and-control behaviour from traffic patterns **without decryption**. Wrote a structured L1 incident report with IOCs, ATT&CK mappings and escalation recommendations.

`Wireshark` `Metasploit` `msfvenom` `Network Forensics` `MITRE ATT&CK`

---

## 💼 Experience

| Role | Company | Period | Highlights |
|---|---|---|---|
| **CSOC Analyst** | Reliance Jio, Navi Mumbai | May 2025 – Aug 2025 | P1–P3 triage within SLA; KQL investigations in Sentinel & Wazuh; endpoint investigations in SentinelOne & Vision One; rule tuning and Python/PowerShell triage automation |
| **Associate Consultant (SOC Analyst)** | Sequretek Solutions, Mumbai | Jun 2024 – Apr 2025 | Multi-source alert triage (SIEM, IDS/IPS, firewall, EDR); PCAP and forensic analysis for IR; false-positive reduction and vulnerability remediation tracking |

---

## 🧰 Tech Stack

**SIEM & Detection**
<p>
  <img src="https://img.shields.io/badge/Microsoft_Sentinel-0078D4?style=flat-square&logo=microsoftazure&logoColor=white"/>
  <img src="https://img.shields.io/badge/Wazuh-3595F9?style=flat-square&logo=wazuh&logoColor=white"/>
  <img src="https://img.shields.io/badge/Splunk-000000?style=flat-square&logo=splunk&logoColor=white"/>
  <img src="https://img.shields.io/badge/IBM_QRadar-052FAD?style=flat-square&logo=ibm&logoColor=white"/>
  <img src="https://img.shields.io/badge/KQL-0078D4?style=flat-square"/>
  <img src="https://img.shields.io/badge/SPL-65A637?style=flat-square"/>
</p>

**EDR / XDR**
<p>
  <img src="https://img.shields.io/badge/SentinelOne-6B0AEA?style=flat-square"/>
  <img src="https://img.shields.io/badge/Trend_Micro_Vision_One-D71920?style=flat-square&logo=trendmicro&logoColor=white"/>
  <img src="https://img.shields.io/badge/Microsoft_Defender-00A4EF?style=flat-square&logo=microsoft&logoColor=white"/>
</p>

**AI Security**
<p>
  <img src="https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white"/>
  <img src="https://img.shields.io/badge/Garak-LLM_scanner-555555?style=flat-square"/>
  <img src="https://img.shields.io/badge/OWASP-LLM_Top_10-000000?style=flat-square&logo=owasp&logoColor=white"/>
  <img src="https://img.shields.io/badge/MITRE-ATLAS-C8102E?style=flat-square"/>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>
</p>

**Forensics, Network & Offensive**
<p>
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white"/>
  <img src="https://img.shields.io/badge/Autopsy-333333?style=flat-square"/>
  <img src="https://img.shields.io/badge/FTK_Imager-444444?style=flat-square"/>
  <img src="https://img.shields.io/badge/Metasploit-2596CD?style=flat-square&logo=metasploit&logoColor=white"/>
  <img src="https://img.shields.io/badge/Nmap-4682B4?style=flat-square"/>
  <img src="https://img.shields.io/badge/Kali_Linux-557C94?style=flat-square&logo=kalilinux&logoColor=white"/>
</p>

**Scripting & Platforms**
<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white"/>
  <img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white"/>
  <img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Microsoft_Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white"/>
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black"/>
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white"/>
</p>

---

## 🏆 Certifications & Education

| | |
|---|---|
| 🎓 **MSc Cyber Security** — National College of Ireland, Dublin (2026) | Network Security · Incident Response · Malware Analysis · Cloud Security · Forensics · Cryptography |
| 🎓 **B.E. Cybersecurity** (Minor in Blockchain) — Shah & Anchor Kutchhi Engineering College, Mumbai (2024) | Malware & Antivirus · Security Policies & Forensics · Web Security · Network Security & Cryptography |
| 🛡️ **Certified Ethical Hacker (CEH v12)** — EC-Council | |
| 🛡️ **Certified Secure Computer User (CSCU)** — EC-Council | |

<p align="left">
  <img src="https://tryhackme-badges.s3.amazonaws.com/ojaspatil10.png" alt="TryHackMe badge"/>
</p>

---

## 🔭 Currently

- 🧪 Extending **LLM-SOC**: ML-based guardrails (Llama Guard), paraphrase-resistant prompt-leak detection, and human-in-the-loop approval for agent tool calls
- 📈 Writing more detection content in **KQL** and **Sigma**
- 💬 Ask me about: **SOC triage, KQL/SPL detections, Wazuh rules, prompt injection, MITRE ATT&CK / ATLAS**

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=ojasmessi&label=Profile%20views&color=0e75b6&style=flat" alt="profile views"/>
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=100&section=footer" alt="footer"/>
</p>
