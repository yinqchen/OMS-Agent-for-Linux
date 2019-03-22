# Operations Management Suite Agent for Linux (2019-02) [![Build Status](https://travis-ci.org/Microsoft/OMS-Agent-for-Linux.png?branch=master)](https://travis-ci.org/Microsoft/OMS-Agent-for-Linux)

## Overview
Welcome to the Log Analytics agent for Linux! The agent for Linux enables rich and real-time analytics for operational data (Syslog, performance, alerts, inventory) from Linux servers, Docker containers and monitoring tools like Nagios, Zabbix and System Center.

## Quick Install guide
The following steps configure setup of the Log Analytics agent in Azure and Azure Government cloud.  *Commands are for 64-bit*. Before installing the Log Analytics agent for Linux, you need the workspace ID and key for your Azure Monitor Log Analytics workspace. 

1. In the Azure portal, click **All services** found in the upper left-hand corner. In the list of resources, type **Log Analytics**. As you begin typing, the list filters based on your input. Select **Log Analytics**.  
2. In your list of Log Analytics workspaces, select the workspace.
3. Select **Advanced settings** from the left hand pane.
4. Select **Connected Sources**, and then select **Linux Servers**. 
5. The value to the right of **Workspace ID** and **Primary Key**. Copy and paste both into your favorite editor. 

To configure the Linux computer to connect to an Azure Monitor Log Analytics workspace, run the following command providing the workspace ID and primary key copied earlier. The following command downloads the agent, validates its checksum, and installs it. 

For Azure Monitor Log Analytics workspace in commercial cloud:
```
wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh && sh onboard_agent.sh -w <YOUR WORKSPACE ID> -s <YOUR WORKSPACE PRIMARY KEY>
```

For Azure Monitor Log Analytics workspace in Azure Government cloud:
```
wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh && sh onboard_agent.sh -w <YOUR WORKSPACE ID> -s <YOUR WORKSPACE PRIMARY KEY> -d opinsights.azure.us
```

## Azure Install guide
If you are an Azure customer, we have an Azure VM extension that allows you to easily onboard to Azure Monitor Log Analytics workspace.
* [Log Analytics Agent for Linux Azure VM extension documentation](https://docs.microsoft.com/azure/virtual-machines/extensions/oms-linux?toc=%2Fazure%2Fazure-monitor%2Ftoc.json)
* [Azure Video walkthrough](https://www.youtube.com/watch?v=mF1wtHPEzT0)

## [Full installation guide](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)

## [Download Latest OMS Agent for Linux (64-bit)](https://github.com/Microsoft/OMS-Agent-for-Linux/releases/download/OMSAgent_v1.9.0-0/omsagent-1.9.0-0.universal.x64.sh)

## [Download Latest OMS Agent for Linux (32-bit)](https://github.com/Microsoft/OMS-Agent-for-Linux/releases/download/OMSAgent_v1.9.0-0/omsagent-1.9.0-0.universal.x86.sh)

## Feedback

We love feedback!  Whether it be good, bad or indifferent, it really helps us build a better product for you.  There are a few different routes to give feedback:

* **UserVoice:** Post ideas for new Azure Monitor logs features to work on [here](http://feedback.azure.com/forums/267889-azure-operational-insights)
* **Monthly survey:** if you are an Azure Monitor customer, you know we send out a survey every month asking our customers about the features we’re working on next.  
* **Elite Linux customer panel:** If you are a die-hard Azure Monitor Linux user and want to join our weekly calls and talk directly to the product team apply through this **[survey](https://www.surveymonkey.com/r/6MTHN3P).**

## Supported Linux Operating Systems

### Supported Distro/Version strategy
The Log Analytics agent for Linux is built to work with Azure Monitor logs, which has a limited scope of scenarios. Our strategy for supporting new distros and versions starting August 2018 is that we will:
1. Only support server versions, no client OS versions.
2. Always support any new [Azure Linux Endorsed distros/versions](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/endorsed-distros).
3. Not support versions that have passed their manufacturer's end-of-support date.
4. Always support the latest GA version of a supported distro.
5. Not support new versions of AMI.
6. Only support versions that run SSL 1.x by default.

If you are using a distro or version that is not currently supported and doesn't fit our future support strategy, we recommend that you fork this repo, acknowledging that Microsoft support will not provide assistance with for forked agent versions.

### 64-bit
* CentOS 6 and 7
* Amazon Linux 2017.09
* Oracle Linux 6 and 7
* Red Hat Enterprise Linux Server 6 and 7
* Debian GNU/Linux 8 and 9
* Ubuntu Linux 14.04 LTS, 16.04 LTS and 18.04 LTS
* SUSE Linux Enterprise Server 12
### 32-bit
* CentOS 6
* Oracle Linux 6
* Red Hat Enterprise Linux Server 6
* Debian GNU/Linux 8 and 9
* Ubuntu Linux 14.04 LTS and 16.04 LTS

**Note:** Openssl 1.1.0 is only supported on x86_64 platforms (64-bit).

**Note:** OpenSSL < 1.x is not supported on any platform.

## [Troubleshooting Guide](https://docs.microsoft.com/azure/azure-monitor/platform/agent-linux-troubleshoot)

## Supported Scenarios
- [Heartbeat data collection](https://docs.microsoft.com/azure/log-analytics/log-analytics-queries?toc=/azure/azure-monitor/toc.json#write-a-query) 
- 
- ### [Syslog data collection](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-syslog) 

- ### [Docker collection](https://docs.microsoft.com/azure/azure-monitor/insights/containers) 

- ### [Performance data collection](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-performance-counters) 

- ### [Nagios and Zabbix alert collection](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-alerts-nagios-zabbix) 

- ### [CollectD Metrics Collection](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-collectd) 

- ### [Custom JSON Data](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-json) 

- ### [VMware Monitoring](https://docs.microsoft.com/azure/azure-monitor/insights/vmware) 

## Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).  For more
information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact
[opencode@microsoft.com](mailto:opencode@microsoft.com) with any
additional questions or comments.
