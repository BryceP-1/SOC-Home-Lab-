# SOC-Home-Lab-

## **Overview**
This project showcases a self built Security Operations Center(SOC) lab using Wazuh SIEM for real time threat dection and monitoring.
The lab simulates common attacks and analyzes how Wazuh detects and alerts those activities.

### **Lab Architecture**
**Environment**: VirtualBox

- **Wazuh server** (SIEM & Alerting Platform)
- **Ubuntu server** (Victim Machine)
- **Kali Linux** (Attacker Machine)

### **Network Configuration**
- **NAT Adapter**: Internet Access
- **Host-only Adapter**: Isolated Attack Network

### **Attacks Simulated**
1. SSH Brute Force Attack
   - Description: Showcased detection of brute force techniques
   - Tool: Hydra
   - Wordlist: rockyou.txt
   - Script: hydra -l <user> -P /usr/share/wordlists/rockyou.txt ssh://<victim_ip>
   - Detection:
     - Multiple failed authentication attempts
     - High severity alerts (Level 8-10)
     - Wazuh Rule IDs: 2502, 2501, 5760, 5758, 40111
2. Persistence - Crontab Modification
   - Description: Showcased detection of persistence techniques
   - Script: sudo crontab -e
   - Detection:
     - Crontab entry changed
     - Crontab opened for editing
     - Wazuh Rule IDs: 2832, 2834
3. Unauthorized User Creation
   - Description: Showcased detection of persistence technique
   - Script: sudo useradd backdoor
             sudo passswd backdoor
   - Detection:
     - New user account created
     - Account modification alerts
   - Wazuh Rule IDs: 5555, 5902
4. Privilege Escalation Attempts
   - Description:
   - Script: sudo -l
             sudo su
   - Detection:
     - Sudo misuse
     - Privilege escalation
   - Wazuh Rule IDs: 5402

### **Key Skills Showcased**
- SIEM deployment and configuration
- Log analysis
- Threat simulation
- Incident response documentation
- Virtual network configuration


     
