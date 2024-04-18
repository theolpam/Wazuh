# Wazuh
# File Integrity Monitoring


A short description of the project

## To start

Wazuh is a security platform that provides unified XDR and SIEM protection for endpoints and cloud workloads. The solution is composed of a single universal agent and three central components: the Wazuh server, the Wazuh indexer, and the Wazuh dashboard.
I advise using the Virtual machine Ubuntu 16.04, 18.04, 20.04, 22.04.
You need to install Quickstart, which contains the Wazuh server, the Wazuh indexer, and the Wazuh dashboard.
Connect to the interface and create the agent.
Test the configuration

## Virtual Machine

You can choose from:

Amazon Linux 2
CentOS 7, 8
Red Hat Enterprise Linux 7, 8, 9
Ubuntu 16.04, 18.04, 20.04, 22.04

Make sure to have at least 4GB of RAM and 2 CPUs during your installation.

## Installation

Download and run the Wazuh installation wizard.

```
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

When the installation is complete, you will have:

INFO: --- Summary ---
INFO: You can access the web interface https://<wazuh-dashboard-ip>
User: admin
Password: password
INFO: Installation finished.

Afterwards, you can connect to the dashboard at: https://<wazuh-dashboard-ip>

## Create an Agent

Select the package to download and install on your system:
Linux/Mac/Windows

Server address:
your <ip> 192.168.1.2

Optional settings:
Name : test

Run the following commands to download and install the agent:
```
Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.7.3-1.msi -OutFile ${env.tmp}\wazuh-agent; msiexec.exe /i ${env.tmp}\wazuh-agent /q WAZUH_MANAGER='192.168.1.2' WAZUH_AGENT_NAME='test' WAZUH_REGISTRATION_SERVER='192.168.1.2'
```

Start the agent:
```
NET START WazuhSvc
```

## Testing of configuration

Follow the steps on your interface:
Modules > Agent > Security Events

Afterwards, you can:

1 : Create a text file in the directory.
2 : Add some content to it.
3 : Delete it.

You'll be able to see that your file has been created, modified, and deleted.

## Authors

* **Theo** _alias_ [@theolpam](https://github.com/theolpam)
