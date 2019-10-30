---
UID: NS:iscsifnd._ISCSI_DiscoveredTarget2
title: _ISCSI_DiscoveredTarget2 (iscsifnd.h)
description: The ISCSI_DiscoveredTarget2 structure contains information that is related to a discovered target device.
old-location: storage\iscsi_discoveredtarget2.htm
tech.root: storage
ms.assetid: 77fb2942-5836-44cb-9a5e-e45f6a022264
ms.date: 03/29/2018
ms.keywords: "*PISCSI_DiscoveredTarget2, ISCSI_DiscoveredTarget2, ISCSI_DiscoveredTarget2 structure [Storage Devices], PISCSI_DiscoveredTarget2, PISCSI_DiscoveredTarget2 structure pointer [Storage Devices], _ISCSI_DiscoveredTarget2, iscsifnd/ISCSI_DiscoveredTarget2, iscsifnd/PISCSI_DiscoveredTarget2, storage.iscsi_discoveredtarget2, structs-iSCSI_5a9fcec3-8447-441c-a2d9-1416c1bbe07e.xml"
ms.topic: struct
f1_keywords:
 - "iscsifnd/ISCSI_DiscoveredTarget2"
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
- ISCSI_DiscoveredTarget2
product:
- Windows
targetos: Windows
req.typenames: ISCSI_DiscoveredTarget2, *PISCSI_DiscoveredTarget2
---

# _ISCSI_DiscoveredTarget2 structure


## -description


The ISCSI_DiscoveredTarget2 structure contains information that is related to a discovered target device. 


## -struct-fields




### -field TargetPortalGroupCount

The number of portal groups that are associated with the target.


### -field TargetName

A name for the target that uniquely identifies the target anywhere in the world. For more information about how to specify this name, see the <i>iSCSI </i>specification that is published by the Internet Engineering Task Force (IETF) of the IP storage working group. 


### -field TargetAlias

The human-readable name or description that is assigned to the target device by its host operating system. You can use this name in user interfaces, but it is not unique, so you should not use it in authentication decisions. 


### -field TargetDiscoveredPortalGroups

A variable-length array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportalgroup2">ISCSI_DiscoveredTargetPortalGroup2</a> structures that contains information about the portal groups that the initiator can use to connect to the target.


## -remarks



The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTarget2 structure when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-discoveredtarget2-wmi-class">ISCSI_DiscoveredTarget2 WMI Class</a> in <i>Discover.mof</i>.

The only difference between the ISCSI_DiscoveredTarget2 structure and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtarget">ISCSI_DiscoveredTarget</a> structure is that the <b>TargetDiscoveredPortalGroups</b> member of ISCSI_DiscoveredTarget2 is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportalgroup2">ISCSI_DiscoveredTargetPortalGroup2</a> structure instead of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportalgroup">ISCSI_DiscoveredTargetPortalGroup</a> structure.  




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtarget">ISCSI_DiscoveredTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-discoveredtarget-wmi-class">ISCSI_DiscoveredTarget WMI Class</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-discoveredtarget2-wmi-class">ISCSI_DiscoveredTarget2 WMI Class</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportalgroup">ISCSI_DiscoveredTargetPortalGroup</a>
 

 

