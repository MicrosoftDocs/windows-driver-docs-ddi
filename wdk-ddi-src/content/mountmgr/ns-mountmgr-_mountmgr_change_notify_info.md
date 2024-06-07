---
UID: NS:mountmgr._MOUNTMGR_CHANGE_NOTIFY_INFO
title: MOUNTMGR_CHANGE_NOTIFY_INFO (mountmgr.h)
description: Learn about the MOUNTMGR_CHANGE_NOTIFY_INFO structure.
tech.root: storage
ms.date: 06/04/2024
keywords: ["MOUNTMGR_CHANGE_NOTIFY_INFO structure"]
ms.keywords: "*PMOUNTMGR_CHANGE_NOTIFY_INFO, MOUNTMGR_CHANGE_NOTIFY_INFO, MOUNTMGR_CHANGE_NOTIFY_INFO structure [Storage Devices], PMOUNTMGR_CHANGE_NOTIFY_INFO, PMOUNTMGR_CHANGE_NOTIFY_INFO structure pointer [Storage Devices], _MOUNTMGR_CHANGE_NOTIFY_INFO, mountmgr/MOUNTMGR_CHANGE_NOTIFY_INFO, mountmgr/PMOUNTMGR_CHANGE_NOTIFY_INFO, storage.mountmgr_change_notify_info, structs-mntmgr_4d6cf8d3-c3cd-4ff5-8ff0-7fac5946d6a5.xml"
req.header: mountmgr.h
req.include-header: Mountmgr.h
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
req.typenames: MOUNTMGR_CHANGE_NOTIFY_INFO, *PMOUNTMGR_CHANGE_NOTIFY_INFO
f1_keywords:
 - _MOUNTMGR_CHANGE_NOTIFY_INFO
 - mountmgr/_MOUNTMGR_CHANGE_NOTIFY_INFO
 - PMOUNTMGR_CHANGE_NOTIFY_INFO
 - mountmgr/PMOUNTMGR_CHANGE_NOTIFY_INFO
 - MOUNTMGR_CHANGE_NOTIFY_INFO
 - mountmgr/MOUNTMGR_CHANGE_NOTIFY_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountmgr.h
api_name:
 - _MOUNTMGR_CHANGE_NOTIFY_INFO
 - PMOUNTMGR_CHANGE_NOTIFY_INFO
 - MOUNTMGR_CHANGE_NOTIFY_INFO
---

## -description

The **MOUNTMGR_CHANGE_NOTIFY_INFO** structure is used by the mount manager to send epic numbers to its clients and vice versa.

## -struct-fields

### -field EpicNumber

Contains the value of a counter used by the mount manager to determine if a client has up-to-date information concerning changes in mount manager's persistent ID database.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[IOCTL_MOUNTMGR_CHANGE_NOTIFY](ni-mountmgr-ioctl_mountmgr_change_notify.md)
