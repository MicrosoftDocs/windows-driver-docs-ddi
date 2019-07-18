---
UID: NS:iscsifnd._ISCSI_DiscoveredTargetPortalGroup
title: _ISCSI_DiscoveredTargetPortalGroup (iscsifnd.h)
description: The ISCSI_DiscoveredTargetPortalGroup structure contains information about a discovered target portal group.
old-location: storage\iscsi_discoveredtargetportalgroup.htm
tech.root: storage
ms.assetid: 5c90dbc2-f42a-4c04-8c77-0ef3a712416c
ms.date: 03/29/2018
ms.keywords: "*PISCSI_DiscoveredTargetPortalGroup, ISCSI_DiscoveredTargetPortalGroup, ISCSI_DiscoveredTargetPortalGroup structure [Storage Devices], PISCSI_DiscoveredTargetPortalGroup, PISCSI_DiscoveredTargetPortalGroup structure pointer [Storage Devices], _ISCSI_DiscoveredTargetPortalGroup, iscsifnd/ISCSI_DiscoveredTargetPortalGroup, iscsifnd/PISCSI_DiscoveredTargetPortalGroup, storage.iscsi_discoveredtargetportalgroup, structs-iSCSI_aa46b46a-73cf-4d06-a5ff-9abc5794f965.xml"
ms.topic: struct
f1_keywords:
 - "iscsifnd/ISCSI_DiscoveredTargetPortalGroup"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsifnd.h
api_name:
- ISCSI_DiscoveredTargetPortalGroup
product:
- Windows
targetos: Windows
req.typenames: ISCSI_DiscoveredTargetPortalGroup, *PISCSI_DiscoveredTargetPortalGroup
---

# _ISCSI_DiscoveredTargetPortalGroup structure


## -description


The ISCSI_DiscoveredTargetPortalGroup structure contains information about a discovered target portal group.


## -struct-fields




### -field PortalCount

The number of portals in the group. 


### -field Portals

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportal">ISCSI_DiscoveredTargetPortal</a> structures, which describe target portals. 


## -remarks



The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortalGroup structure when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-discoveredtargetportalgroup-wmi-class">ISCSI_DiscoveredTargetPortalGroup WMI Class</a> in <i>Discover.mof</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportal">ISCSI_DiscoveredTargetPortal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-discoveredtargetportalgroup-wmi-class">ISCSI_DiscoveredTargetPortalGroup WMI Class</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportalgroup2">ISCSI_DiscoveredTargetPortalGroup2</a>
 

 

