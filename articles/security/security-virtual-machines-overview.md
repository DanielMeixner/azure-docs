﻿---
title: Azure security features used with Azure virtual machines | Microsoft Docs
description: This article provides an overview of the core Azure security features that can be used with Azure Virtual Machines.
services: security
documentationcenter: na
author: TerryLanfear
manager: MBaldwin
editor: TomSh

ms.assetid: 467b2c83-0352-4e9d-9788-c77fb400fe54
ms.service: security
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/21/2017
ms.author: terrylan

---
# Azure Virtual Machines security overview
You can use Azure Virtual Machines to deploy a wide range of computing solutions in an agile way. The service supports Microsoft Windows, Linux, Microsoft SQL Server, Oracle, IBM, SAP, and Azure BizTalk Services. So you can deploy any workload and any language on nearly any operating system.

An Azure virtual machine gives you the flexibility of virtualization without having to buy and maintain the physical hardware that runs the virtual machine. You can build and deploy your applications with the assurance that your data is protected and safe in highly secure datacenters.

With Azure, you can build security-enhanced, compliant solutions that:

* Protect your virtual machines from viruses and malware.
* Encrypt your sensitive data.
* Secure network traffic.
* Identify and detect threats.
* Meet compliance requirements.

The goal of this article is to provide an overview of the core Azure security features that can be used with virtual machines. Links to articles give details of each feature so you can learn more.  

## Antimalware
With Azure, you can use antimalware software from security vendors such as Microsoft, Symantec, Trend Micro, and Kaspersky. This software helps protect your virtual machines from malicious files, adware, and other threats.

Microsoft Antimalware for Azure Cloud Services and Virtual Machines is a real-time protection capability that helps identify and remove viruses, spyware, and other malicious software.  Microsoft Antimalware for Azure provides configurable alerts when known malicious or unwanted software attempts to install itself or run on your Azure systems.

Microsoft Antimalware for Azure is a single-agent solution for applications and tenant environments. It's designed to run in the background without human intervention. You can deploy protection based on the needs of your application workloads, with either basic secure-by-default or advanced custom configuration, including antimalware monitoring.

When you deploy and enable Microsoft Antimalware for Azure, the following core features are available:

* **Real-time protection**: Monitors activity in Cloud Services and on Virtual Machines to detect and block malware execution.
* **Scheduled scanning**: Periodically performs targeted scanning to detect malware, including actively running programs.
* **Malware remediation**: Automatically takes action on detected malware, such as deleting or quarantining malicious files and cleaning up malicious registry entries.
* **Signature updates**: Automatically installs the latest protection signatures (virus definitions) to ensure that protection is up-to-date on a pre-determined frequency.
* **Antimalware engine updates**: Automatically updates the Microsoft Antimalware for Azure engine.
* **Antimalware platform updates**: Automatically updates the Microsoft Antimalware for Azure platform.
* **Active protection**: Reports telemetry metadata to Azure about detected threats and suspicious resources to ensure rapid response. Enables real-time synchronous signature delivery through the Microsoft Active Protection System (MAPS).
* **Samples reporting**: Provides and reports samples to the Microsoft Antimalware for Azure service to help refine the service and enable troubleshooting.
* **Exclusions**: Allows application and service administrators to configure certain files, processes, and drives to exclude them from protection and scanning for performance and other reasons.
* **Antimalware event collection**: Records antimalware service health, suspicious activities, and remediation actions taken in the operating system event log and collects them in your Azure storage account.

Learn more about antimalware software to help protect your virtual machines:

* [Microsoft Antimalware for Azure Cloud Services and Virtual Machines](azure-security-antimalware.md)
* [Deploying Antimalware Solutions on Azure Virtual Machines](https://azure.microsoft.com/blog/deploying-antimalware-solutions-on-azure-virtual-machines/)
* [How to install and configure Trend Micro Deep Security as a service on a Windows VM](../virtual-machines/windows/classic/install-trend.md)
* [How to install and configure Symantec Endpoint Protection on a Windows VM](../virtual-machines/windows/classic/install-symantec.md)
* [Security solutions in the Azure Marketplace](https://azure.microsoft.com/marketplace/?term=security)

## Hardware security module
Improving key security can enhance encryption and authentication protections. You can simplify the management and security of your critical secrets and keys by storing them in Azure Key Vault. 

Key Vault provides the option to store your keys in hardware security modules (HSMs) certified to FIPS 140-2 Level 2 standards. Your SQL Server encryption keys for backup or [transparent data encryption](https://msdn.microsoft.com/library/bb934049.aspx) can all be stored in Key Vault with any keys or secrets from your applications. Permissions and access to these protected items are managed through [Azure Active Directory](https://azure.microsoft.com/documentation/services/active-directory/).

Learn more:

* [What is Azure Key Vault?](../key-vault/key-vault-whatis.md)
* [Get started with Azure Key Vault](../key-vault/key-vault-get-started.md)
* [Azure Key Vault blog](https://blogs.technet.microsoft.com/kv/)

## Virtual machine disk encryption
Azure Disk Encryption is a new capability for encrypting your Windows and Linux virtual machine disks. Azure Disk Encryption uses the industry-standard [BitLocker](https://technet.microsoft.com/library/cc732774.aspx) feature of Windows and the [dm-crypt](https://en.wikipedia.org/wiki/Dm-crypt) feature of Linux to provide volume encryption for the OS and the data disks.

The solution is integrated with Azure Key Vault to help you control and manage the disk encryption keys and secrets in your key vault subscription. It ensures that all data in the virtual machine disks are encrypted at rest in Azure Storage.

Learn more:

* [Azure Disk Encryption for Windows and Linux IaaS VMs](https://gallery.technet.microsoft.com/Azure-Disk-Encryption-for-a0018eb0)
* [Azure Disk Encryption for Linux and Windows Virtual Machines](https://blogs.msdn.microsoft.com/azuresecurity/2015/11/16/azure-disk-encryption-for-linux-and-windows-virtual-machines-public-preview-now-available/)
* [Encrypt a virtual machine](../security-center/security-center-disk-encryption.md)

## Virtual machine backup
Azure Backup is a scalable solution that helps protect your application data with zero capital investment and minimal operating costs. Application errors can corrupt your data, and human errors can introduce bugs into your applications. With Azure Backup, your virtual machines running Windows and Linux are protected.

Learn more:

* [What is Azure Backup?](../backup/backup-introduction-to-azure-backup.md)
* [Azure Backup Learning Path](https://azure.microsoft.com/documentation/learning-paths/backup/)
* [Azure Backup service FAQ](../backup/backup-azure-backup-faq.md)

## Azure Site Recovery
An important part of your organization's BCDR strategy is figuring out how to keep corporate workloads and apps running when planned and unplanned outages occur. Azure Site Recovery helps orchestrate replication, failover, and recovery of workloads and apps so that they're available from a secondary location if your primary location goes down.

Site Recovery:

* **Simplifies your BCDR strategy**: Site Recovery makes it easy to handle replication, failover, and recovery of multiple business workloads and apps from a single location. Site Recovery orchestrates replication and failover but doesn't intercept your application data or have any information about it.
* **Provides flexible replication**: By using Site Recovery, you can replicate workloads running on Hyper-V virtual machines, VMware virtual machines, and Windows/Linux physical servers.
* **Supports failover and recovery**: Site Recovery provides test failovers to support disaster recovery drills without affecting production environments. You can also run planned failovers with a zero-data loss for expected outages, or unplanned failovers with minimal data loss (depending on replication frequency) for unexpected disasters. After failover, you can fail back to your primary sites. Site Recovery provides recovery plans that can include scripts and Azure automation workbooks so that you can customize failover and recovery of multi-tier applications.
* **Eliminates secondary datacenters**: You can replicate to a secondary on-premises site, or to Azure. Using Azure as a destination for disaster recovery eliminates the cost and complexity of maintaining a secondary site. Replicated data is stored in Azure Storage.
* **Integrates with existing BCDR technologies**: Site Recovery partners with other applications' BCDR features. For example, you can use Site Recovery to help protect the SQL Server back end of corporate workloads. This includes native support for SQL Server Always On to manage the failover of availability groups.

Learn more:

* [What is Azure Site Recovery?](../site-recovery/site-recovery-overview.md)
* [How does Azure Site Recovery work?](../site-recovery/site-recovery-components.md)
* [What workloads are protected by Azure Site Recovery?](../site-recovery/site-recovery-workload.md)

## Virtual networking
Virtual machines need network connectivity. To support that requirement, Azure requires virtual machines to be connected to an Azure virtual network. 

An Azure virtual network is a logical construct built on top of the physical Azure network fabric. Each logical Azure virtual network is isolated from all other Azure virtual networks. This isolation helps insure that network traffic in your deployments is not accessible to other Microsoft Azure customers.

Learn more:

* [Azure network security overview](security-network-overview.md)
* [Virtual Network overview](../virtual-network/virtual-networks-overview.md)
* [Networking features and partnerships for enterprise scenarios](https://azure.microsoft.com/blog/networking-enterprise/)

## Security policy management and reporting
Azure Security Center helps you prevent, detect, and respond to threats. Security Center gives you increased visibility into, and control over, the security of your Azure resources. It provides integrated security monitoring and policy management across your Azure subscriptions. It helps detect threats that might otherwise go unnoticed, and works with a broad ecosystem of security solutions.

Security Center helps you optimize and monitor the security of your virtual machines by:

* Providing [security recommendations](../security-center/security-center-recommendations.md) for the virtual machines. Example recommendations include: apply system updates, configure ACLs endpoints, enable antimalware, enable network security groups, and apply disk encryption.
* Monitoring the state of your virtual machines.

Learn more:

* [Introduction to Azure Security Center](../security-center/security-center-intro.md)
* [Azure Security Center frequently asked questions](../security-center/security-center-faq.md)
* [Azure Security Center planning and operations](../security-center/security-center-planning-and-operations-guide.md)

## Compliance
Azure Virtual Machines is certified for FISMA, FedRAMP, HIPAA, PCI DSS Level 1, and other key compliance programs. This certification makes it easier for your own Azure applications to meet compliance requirements and for your business to address a wide range of domestic and international regulatory requirements.

Learn more:

* [Microsoft Trust Center: Compliance](https://www.microsoft.com/TrustCenter/Compliance/default.aspx)
* [Trusted Cloud: Microsoft Azure Security, Privacy, and Compliance](http://download.microsoft.com/download/1/6/0/160216AA-8445-480B-B60F-5C8EC8067FCA/WindowsAzure-SecurityPrivacyCompliance.pdf)
