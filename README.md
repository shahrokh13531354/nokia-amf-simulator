Nokia CMM AMF CLI Simulator
> An interactive, browser-based CLI simulator for practicing Nokia Cloud Mobility Manager (CMM) AMF commands — no installation required.
![Nokia CMM AMF Simulator](https://img.shields.io/badge/Nokia-CMM24.3-005AFF?style=flat-square&logo=nokia&logoColor=white)
![HTML](https://img.shields.io/badge/Built%20with-HTML%2FJS-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-brightgreen?style=flat-square)
---
Live Demo
Launch Simulator
https://shahrokh13531354.github.io/nokia-amf-simulator/nokia_amf_simulator_v4.html

About
This simulator replicates the Nokia CMM command-line interface used to manage the Access and Mobility Management Function (AMF) in a 5G Core network. It is designed as a hands-on practice environment for telecom engineers preparing for lab work, certification, or day-to-day operations on Nokia CMM24.3.
It runs entirely in the browser — no server, no installation, no Nokia hardware required.

Features
Authentic CLI feel — matches the real `cmm <object> <action> [--param value]` syntax
Tab autocomplete — press Tab to complete commands, just like the real NECC shell
Command history — use ↑ / ↓ arrow keys to cycle through previous commands
Realistic table output — color-coded tables matching actual CMM show/list outputs
Live alarm simulation — active MAJOR N26 alarm to practice full troubleshooting workflow
Sidebar + Quick Commands — clickable shortcuts for the most common operations
Guided tutorial — type `tutorial` for a step-by-step N26 fault investigation walkthrough
Node status dashboard — live AMF identity panel, interface health, and alarm feed
---
🛠️ Supported Commands
AMF Management
```
cmm amfMultiLink list [--amfIntfType {N2,N8,N11,N12,N14,N15,N26,Nnrf,...}]
cmm amfMultiLink show --amfIntfType N2 --linkIndex 1
cmm amfLinkAdmin show --amfLinkType {N2,N26,SBI_Client,SBI_Server}
cmm amfLinkAdmin modify --amfLinkType N2 --linkIndex 1 --amfLinkAdminState {blocked,locked,unlocked}
cmm amfGParms show --amfGparmName <name>
cmm amfGParms list
cmm amfGParms modify --amfGparmName <name> --amfGparmValue <value>
cmm amfCapacityGParms show --amfGparmName amfRelativeCapacity
```
UE & Subscribers
```
cmm ueContext list
cmm ueContext show --imsi <imsi>
cmm ueContextCount list
```
Network Configuration
```
cmm plmn list | show --plmnName <name>
cmm tai list | create --plmnName <name> --tac <tac> | delete
cmm allowedSnssai list
cmm rmtEndPtCfg list | create --name <n> --interfaceName <i> --ip1 <ip>
cmm localEndPtCfg list | create --interfaceName <i> [--multiHomed {true,false}]
cmm amfEplmn list
cmm serviceIp list
```
Alarms & Fault Management
```
cmm alarmActive list | show --alarmId <id>
cmm alarmHistory list
cmm alarmDefinition show --alarmId <id>
cmm alarmIgnore create --alarmId <id>
```
Diagnostics & Connectivity
```
cmm nbiPing list --pingTarget <ip> --pingSourceIp <ip>
cmm amfHttp2Ping list --amfClientIntf N8 --amfRmtEndIp <ip> --amfRmtEndIpPort 8080
cmm sbiConnectionTestUri list --targetUri <uri> --endPointName N8
cmm clusterMgmt test.ping --target '*'
```
Performance & Monitoring
```
cmm gParms show --gParmName enablePrometheusGW
cmm prometheusGW list
cmm firewallRule list
cmm counter show <counterId>
```
System
```
cmm authenticate
cmm diamProfile list | create
cmm amfEmergencyProfile list
sudo pcs status
sudo journalctl -u <service>
```
---
🎓 Guided Tutorial
Type `tutorial` in the simulator to launch a step-by-step walkthrough that covers:
Checking and interpreting active alarms
Reading alarm definitions and corrective actions
Verifying N26 link status
Running NBI ping to check IP connectivity
Reviewing AMF capacity parameters
Monitoring UE context counts
---
Keyboard Shortcuts
Key	Action
`Tab`	Autocomplete command
`↑` / `↓`	Navigate command history
`Ctrl + L`	Clear terminal
`Enter`	Execute command
---
Project Structure
```
nokia-amf-simulator/
│
├── index.html      # Entire simulator — single self-contained file
└── README.md       # This file
```
No build step. No npm. No frameworks. Just open `index.html` in any modern browser.
---
Technology
Pure HTML / CSS / JavaScript — zero dependencies
JetBrains Mono & Share Tech Mono fonts via Google Fonts
Designed for Chromium-based browsers and Firefox
---
Author
Shahrokh Omalie
Senior Solutions Architect | 5G Core & Cloud-Native Telco
Toronto, ON · LinkedIn · GitHub
20+ years of hands-on experience with Nokia CMM, EPC, IMS, and 5G Core deployments across Bell Mobility, TELUS, SaskTel, Freedom Mobile, and AT&T.
---
 Disclaimer
This is an unofficial, independent project created for educational and practice purposes only.
Not affiliated with, endorsed by, or sponsored by Nokia
Command names and parameter structures reflect publicly documented 3GPP/telecom interfaces
All IP addresses, IMSI values, and network data shown are fictional examples
Do not use this tool for production network management
---
License
MIT License — free to use, modify, and share with attribution.
---
Contributing
Found a missing command? Want to add MME or SGSN mode? PRs are welcome.
Fork the repo
Edit `index.html` — add your command in the `dispatchCmm()` function
Open a pull request with a brief description
---
Built by Shahrokh Omali, for Nokia engineers.
