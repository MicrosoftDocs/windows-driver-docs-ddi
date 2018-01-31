---
UID: NS:iscsicfg._MSiSCSI_DiscoveryConfig
title: "_MSiSCSI_DiscoveryConfig"
author: windows-driver-content
description: The MSiSCSI_DiscoveryConfig structure contains information that indicates what methods an initiator uses to do discovery.
old-location: storage\msiscsi_discoveryconfig.htm
old-project: storage
ms.assetid: fe2f4a93-3fdd-422b-afce-8def3ed6688e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-iSCSI_b27b8a7d-40bd-40a7-b9d8-3e49bbc8497f.xml, *PMSiSCSI_DiscoveryConfig, MSiSCSI_DiscoveryConfig structure [Storage Devices], iscsicfg/MSiSCSI_DiscoveryConfig, PMSiSCSI_DiscoveryConfig structure pointer [Storage Devices], storage.msiscsi_discoveryconfig, PMSiSCSI_DiscoveryConfig, _MSiSCSI_DiscoveryConfig, iscsicfg/PMSiSCSI_DiscoveryConfig, MSiSCSI_DiscoveryConfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsicfg.h
req.include-header: Iscsicfg.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsicfg.h
apiname:
-	MSiSCSI_DiscoveryConfig
product: Windows
targetos: Windows
req.typenames: MSiSCSI_DiscoveryConfig, *PMSiSCSI_DiscoveryConfig
---

# _MSiSCSI_DiscoveryConfig structure


## -description


The MSiSCSI_DiscoveryConfig structure contains information that indicates what methods an initiator uses to do discovery.


## -syntax


````
typedef struct _MSiSCSI_DiscoveryConfig {
  BOOLEAN          PerformiSNSDiscovery;
  BOOLEAN          PerformSLPDiscovery;
  BOOLEAN          AutomaticiSNSDiscovery;
  WCHAR            InitiatorName[256 + 1];
  ISCSI_IP_Address iSNSServer;
} MSiSCSI_DiscoveryConfig, *PMSiSCSI_DiscoveryConfig;
````


## -struct-fields




#### - PerformiSNSDiscovery

A Boolean value that indicates whether the initiator performs target discovery by using iSNS and a predetermined iSNS server. If this member is <b>TRUE</b>, the initiator performs target discovery by using iSNS and a predetermined iSNS server. If this member is <b>FALSE</b>, the initiator does not do discovery with iSNS.


#### - PerformSLPDiscovery

A Boolean value that indicates whether the initiator performs target discovery by using SLP. If this member is <b>TRUE</b>, the initiator performs target discovery by using SLP. 


#### - AutomaticiSNSDiscovery

A Boolean value that indicates whether the initiator should automatically search for an iSNS server and then perform target discovery by using iSNS. If this member is <b>TRUE</b>, the initiator should automatically search for an iSNS server and then perform target discovery by using iSNS.


#### - InitiatorName

The default initiator name to register with the iSNS server. 


#### - iSNSServer

If <b>AutomaticiSNSDiscovery</b> is <b>FALSE</b>, <b>iSNSServer</b> contains a <a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a> structure that provides a fixed address of the iSNS server that is independent of the version of the IP protocol in use. 


## -remarks


The WMI tool suite automatically generates a declaration of the MSiSCSI_DiscoveryConfig structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562995">MSiSCSI_DiscoveryConfig WMI Class</a> in <i>Config.mof</i>. 

Initiators are required to implement the MSiSCSI_DiscoveryConfig class. You must implement this class.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562995">MSiSCSI_DiscoveryConfig WMI Class</a>

<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_DiscoveryConfig structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

