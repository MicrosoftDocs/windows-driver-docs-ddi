---
UID: NS:iscsicfg._MSiSCSI_DiscoveryConfig
title: _MSiSCSI_DiscoveryConfig (iscsicfg.h)
description: The MSiSCSI_DiscoveryConfig structure contains information that indicates what methods an initiator uses to do discovery.
old-location: storage\msiscsi_discoveryconfig.htm
tech.root: storage
ms.assetid: fe2f4a93-3fdd-422b-afce-8def3ed6688e
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_DiscoveryConfig, MSiSCSI_DiscoveryConfig, MSiSCSI_DiscoveryConfig structure [Storage Devices], PMSiSCSI_DiscoveryConfig, PMSiSCSI_DiscoveryConfig structure pointer [Storage Devices], _MSiSCSI_DiscoveryConfig, iscsicfg/MSiSCSI_DiscoveryConfig, iscsicfg/PMSiSCSI_DiscoveryConfig, storage.msiscsi_discoveryconfig, structs-iSCSI_b27b8a7d-40bd-40a7-b9d8-3e49bbc8497f.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsicfg.h
api_name:
-	MSiSCSI_DiscoveryConfig
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_DiscoveryConfig, *PMSiSCSI_DiscoveryConfig
---

# _MSiSCSI_DiscoveryConfig structure


## -description


The MSiSCSI_DiscoveryConfig structure contains information that indicates what methods an initiator uses to do discovery.


## -struct-fields




### -field PerformiSNSDiscovery

A Boolean value that indicates whether the initiator performs target discovery by using iSNS and a predetermined iSNS server. If this member is <b>TRUE</b>, the initiator performs target discovery by using iSNS and a predetermined iSNS server. If this member is <b>FALSE</b>, the initiator does not do discovery with iSNS.


### -field PerformSLPDiscovery

A Boolean value that indicates whether the initiator performs target discovery by using SLP. If this member is <b>TRUE</b>, the initiator performs target discovery by using SLP. 


### -field AutomaticiSNSDiscovery

A Boolean value that indicates whether the initiator should automatically search for an iSNS server and then perform target discovery by using iSNS. If this member is <b>TRUE</b>, the initiator should automatically search for an iSNS server and then perform target discovery by using iSNS.


### -field InitiatorName

The default initiator name to register with the iSNS server. 


### -field iSNSServer

If <b>AutomaticiSNSDiscovery</b> is <b>FALSE</b>, <b>iSNSServer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a> structure that provides a fixed address of the iSNS server that is independent of the version of the IP protocol in use. 


## -remarks



The WMI tool suite automatically generates a declaration of the MSiSCSI_DiscoveryConfig structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562995">MSiSCSI_DiscoveryConfig WMI Class</a> in <i>Config.mof</i>. 

Initiators are required to implement the MSiSCSI_DiscoveryConfig class. You must implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562995">MSiSCSI_DiscoveryConfig WMI Class</a>
 

 

