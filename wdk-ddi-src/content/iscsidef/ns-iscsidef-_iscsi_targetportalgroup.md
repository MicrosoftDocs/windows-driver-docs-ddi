---
UID: NS:iscsidef._ISCSI_TargetPortalGroup
title: _ISCSI_TargetPortalGroup (iscsidef.h)
description: The ISCSI_TargetPortalGroup structure provides a definition of a target portal group.
old-location: storage\iscsi_targetportalgroup.htm
tech.root: storage
ms.assetid: 28f48224-90b8-45f5-b69d-6bb6a34f64e0
ms.date: 03/29/2018
keywords: ["_ISCSI_TargetPortalGroup structure"]
ms.keywords: "*PISCSI_TargetPortalGroup, ISCSI_TargetPortalGroup, ISCSI_TargetPortalGroup structure [Storage Devices], PISCSI_TargetPortalGroup, PISCSI_TargetPortalGroup structure pointer [Storage Devices], _ISCSI_TargetPortalGroup, iscsidef/ISCSI_TargetPortalGroup, iscsidef/PISCSI_TargetPortalGroup, storage.iscsi_targetportalgroup, structs-iSCSI_27b8d554-5021-49d0-837c-302e7ac033ed.xml"
f1_keywords:
 - "iscsidef/ISCSI_TargetPortalGroup"
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
- iscsidef.h
api_name:
- ISCSI_TargetPortalGroup
product:
- Windows
targetos: Windows
req.typenames: ISCSI_TargetPortalGroup, *PISCSI_TargetPortalGroup
---

# _ISCSI_TargetPortalGroup structure


## -description


The ISCSI_TargetPortalGroup structure provides a definition of a target portal group. 


## -struct-fields




### -field PortalCount

The number of portals in the portal group. 


### -field Portals

A variable-length array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_targetportal">ISCSI_TargetPortal</a> structures, which describe portals in the target portal group. The number of elements in the array is specified by the PortalCount field.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_targetportal">ISCSI_TargetPortal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-targetportalgroup-wmi-class">ISCSI_TargetPortalGroup WMI Class</a>
 

 

