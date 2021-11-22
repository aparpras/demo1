# ansible-project-gts-cm-calibration
![stability-stable](https://img.shields.io/badge/stability-stable-green.svg)

[Ansible](https://www.ansible.com/) is a configuration management tool. It automates the configuration and management of infrastructure components such as servers and network switches.

GTS Compliance Managemnent (GCM) is the strategic GTS solution for Security Health Checking and Remediation of **servers** adhering to ITSS/CSD security standards. The files in this repository serve as a template for your Account's Ansible secuirty and compliance projects. Once you've customized the configuration files, servers can be health checked quickly and consistently.

## Using this repository
The latest GCM release can be seen in the [Coverage Page](https://pages.github.kyndryl.net/Continuous-Engineering/GTS-Compliance-Management/coverage) details on the GCM wiki. Please switch to the branch corresponding to the version of GCM that you require (eg. v5.3.0).

Please see the GCM User's Guide available here:
[GCM For Ansible User Guide](https://pages.github.kyndryl.net/Continuous-Engineering/GTS-Compliance-Management/assets/docs/GCM%20for%20Ansible%20Users%20Guide.pdf)

## Dependencies
The standard CACF prerequisites, including the BDS (Binary Distribution Service) on **all** Account Jump Hosts, must be deployed and configured before GCM can be used from Ansible Tower.

## Health Check Scanner Exit Codes
The Health Check scan exit code can be checked from the Ansible job log or from HCLauncher.log.

Exit Code | Success? | Comments
----------|----------|----------------------------------------------------
0         | True     | All Ok
1         | False    | HCLauncher error
2         | False    | Collector error
3         | False    | Collector and HCLauncher error
4         | False    | SQL error
5         | False    | SQL and HCLauncher error
6         | False    | SQL and Collector error
7         | False    | SQL, Collector and HCLauncher error
8         | unknown  | Remote device connection error
9         | False    | Ansible Scan task timeout
194       | True     | Remediation requires server reboot (UNIX only)
195       | True     | Remediation requires daemon restart (UNIX only)
999       | True     | Remediation aborted - GPO controlled setting (Windows only)
3010      | True     | Remediation requires server reboot (Windows only)
3011      | True     | Remediation requires service restart (Windows only)

## How to create a Bug report / Enhancement request
To open a bug / enhancement for GCM functionality or coverage, please click the **"Submit New"** button in the top right of the [GCM website](https://pages.github.kyndryl.net/Continuous-Engineering/GTS-Compliance-Management).

## License
See [license.md](https://github.kyndryl.net/Continuous-Engineering/ansible-project-gts-cm-calibration/blob/master/license.md)

## Author
Author: GCM Dev Team
