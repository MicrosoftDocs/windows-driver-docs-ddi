---
UID: NS:iscsifnd._ISCSI_DiscoveredTargetPortal
title: "_ISCSI_DiscoveredTargetPortal"
author: windows-driver-content
description: The ISCSI_DiscoveredTargetPortal structure provides information that is associated with a discovered target portal.
old-location: storage\iscsi_discoveredtargetportal.htm
tech.root: storage
ms.assetid: af5d0ad6-a035-4291-9390-889fdc3429ee
ms.date: 3/29/2018
ms.keywords: "*PISCSI_DiscoveredTargetPortal, ISCSI_DiscoveredTargetPortal, ISCSI_DiscoveredTargetPortal structure [Storage Devices], PISCSI_DiscoveredTargetPortal, PISCSI_DiscoveredTargetPortal structure pointer [Storage Devices], _ISCSI_DiscoveredTargetPortal, iscsifnd/ISCSI_DiscoveredTargetPortal, iscsifnd/PISCSI_DiscoveredTargetPortal, storage.iscsi_discoveredtargetportal, structs-iSCSI_956c4a5b-9f37-4b76-b2e8-d8feedaddcf0.xml"
ms.topic: struct
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
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
-	iscsifnd.h
api_name:
-	ISCSI_DiscoveredTargetPortal
product:
- Windows
targetos: Windows
req.typenames: ISCSI_DiscoveredTargetPortal, *PISCSI_DiscoveredTargetPortal
---

# _ISCSI_DiscoveredTargetPortal structure


## -description


The ISCSI_DiscoveredTargetPortal structure provides information that is associated with a discovered target portal. 


## -struct-fields




### -field Socket

The socket number of the portal. 


### -field Address

The network address of the portal. 


### -field SymbolicName

A wide character string that indicates the portal's symbolic name.


## -remarks



The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortal structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561524">ISCSI_DiscoveredTargetPortal WMI Class</a> in <i>Discover.mof</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561524">ISCSI_DiscoveredTargetPortal WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561511">ISCSI_DiscoveredTargetPortal2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561574">ISCSI_TargetPortal</a>
 

 

