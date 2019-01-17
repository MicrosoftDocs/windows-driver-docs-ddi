---
UID: NS:iscsifnd._ISCSI_DiscoveredTargetPortalGroup2
title: "_ISCSI_DiscoveredTargetPortalGroup2"
description: The ISCSI_DiscoveredTargetPortalGroup2 structure contains information about a discovered target portal group.
old-location: storage\iscsi_discoveredtargetportalgroup2.htm
tech.root: storage
ms.assetid: d852f062-3090-4a7a-bdb8-9dde93257a90
ms.date: 03/29/2018
ms.keywords: "*PISCSI_DiscoveredTargetPortalGroup2, ISCSI_DiscoveredTargetPortalGroup2, ISCSI_DiscoveredTargetPortalGroup2 structure [Storage Devices], PISCSI_DiscoveredTargetPortalGroup2, PISCSI_DiscoveredTargetPortalGroup2 structure pointer [Storage Devices], _ISCSI_DiscoveredTargetPortalGroup2, iscsifnd/ISCSI_DiscoveredTargetPortalGroup2, iscsifnd/PISCSI_DiscoveredTargetPortalGroup2, storage.iscsi_discoveredtargetportalgroup2, structs-iSCSI_2135fea1-a4b9-401e-a7b3-9a1b1896fe28.xml"
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
-	ISCSI_DiscoveredTargetPortalGroup2
product:
- Windows
targetos: Windows
req.typenames: ISCSI_DiscoveredTargetPortalGroup2, *PISCSI_DiscoveredTargetPortalGroup2
---

# _ISCSI_DiscoveredTargetPortalGroup2 structure


## -description


The ISCSI_DiscoveredTargetPortalGroup2 structure contains information about a discovered target portal group.


## -struct-fields




### -field PortalCount

The number of portals in the group. 


### -field Tag

A tag number that identifies the portal group. 


### -field Portals

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561509">ISCSI_DiscoveredTargetPortal</a> structures, which describe target portals. 


## -remarks



The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortalGroup2 structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561520">ISCSI_DiscoveredTargetPortalGroup2 WMI Class</a> in <i>Discover.mof</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561509">ISCSI_DiscoveredTargetPortal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561515">ISCSI_DiscoveredTargetPortalGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561523">ISCSI_DiscoveredTargetPortalGroup WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561520">ISCSI_DiscoveredTargetPortalGroup2 WMI Class</a>
 

 

