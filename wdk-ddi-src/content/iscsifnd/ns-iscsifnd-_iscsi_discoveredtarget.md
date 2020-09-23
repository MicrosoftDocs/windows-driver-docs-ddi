---
UID: NS:iscsifnd._ISCSI_DiscoveredTarget
title: _ISCSI_DiscoveredTarget (iscsifnd.h)
description: The ISCSI_DiscoveredTarget structure contains information that is related to a discovered target device.
old-location: storage\iscsi_discoveredtarget.htm
tech.root: storage
ms.assetid: 0b4a7375-1ee2-4829-92bb-01ed610236de
ms.date: 03/29/2018
keywords: ["ISCSI_DiscoveredTarget structure"]
ms.keywords: "*PISCSI_DiscoveredTarget, ISCSI_DiscoveredTarget, ISCSI_DiscoveredTarget structure [Storage Devices], PISCSI_DiscoveredTarget, PISCSI_DiscoveredTarget structure pointer [Storage Devices], _ISCSI_DiscoveredTarget, iscsifnd/ISCSI_DiscoveredTarget, iscsifnd/PISCSI_DiscoveredTarget, storage.iscsi_discoveredtarget, structs-iSCSI_d53d59a0-bd96-4eb8-b874-5846302ddda2.xml"
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
targetos: Windows
req.typenames: ISCSI_DiscoveredTarget, *PISCSI_DiscoveredTarget
f1_keywords:
 - _ISCSI_DiscoveredTarget
 - iscsifnd/_ISCSI_DiscoveredTarget
 - PISCSI_DiscoveredTarget
 - iscsifnd/PISCSI_DiscoveredTarget
 - ISCSI_DiscoveredTarget
 - iscsifnd/ISCSI_DiscoveredTarget
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsifnd.h
api_name:
 - ISCSI_DiscoveredTarget
---

# _ISCSI_DiscoveredTarget structure


## -description

The ISCSI_DiscoveredTarget structure contains information that is related to a discovered target device.

## -struct-fields

### -field TargetPortalGroupCount

The number of portal groups that are associated with the target.

### -field TargetName

A name for the target that uniquely identifies the target anywhere in the world. For information about how to specify this name, see the <i>iSCSI </i>specification that is published by the Internet Engineering Task Force (IETF) of the IP storage working group.

### -field TargetAlias

The human-readable name or description that is assigned to the target device by its host operating system. You can use this name in user interfaces, but it is not unique, you should not use it in authentication decisions.

### -field TargetDiscoveredPortalGroups

A variable-length array of <a href="/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportalgroup">ISCSI_DiscoveredTargetPortalGroup</a> structures that contains information about the portal groups that the initiator can use to connect to the target.

## -remarks

The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTarget structure when it compiles the <a href="/windows-hardware/drivers/storage/iscsi-discoveredtarget-wmi-class">ISCSI_DiscoveredTarget WMI Class</a> in <i>Discover.mof</i>.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-discoveredtarget-wmi-class">ISCSI_DiscoveredTarget WMI Class</a>



<a href="/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtarget2">ISCSI_DiscoveredTarget2</a>



<a href="/windows-hardware/drivers/ddi/iscsifnd/ns-iscsifnd-_iscsi_discoveredtargetportalgroup">ISCSI_DiscoveredTargetPortalGroup</a>