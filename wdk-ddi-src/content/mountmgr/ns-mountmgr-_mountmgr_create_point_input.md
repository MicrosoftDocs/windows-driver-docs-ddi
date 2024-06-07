---
UID: NS:mountmgr._MOUNTMGR_CREATE_POINT_INPUT
title: MOUNTMGR_CREATE_POINT_INPUT (mountmgr.h)
description: Learn about the MOUNTMGR_CREATE_POINT_INPUT structure.
tech.root: storage
ms.date: 06/04/2024
keywords: ["MOUNTMGR_CREATE_POINT_INPUT structure"]
ms.keywords: "*PMOUNTMGR_CREATE_POINT_INPUT, MOUNTMGR_CREATE_POINT_INPUT, MOUNTMGR_CREATE_POINT_INPUT structure [Storage Devices], PMOUNTMGR_CREATE_POINT_INPUT, PMOUNTMGR_CREATE_POINT_INPUT structure pointer [Storage Devices], _MOUNTMGR_CREATE_POINT_INPUT, mountmgr/MOUNTMGR_CREATE_POINT_INPUT, mountmgr/PMOUNTMGR_CREATE_POINT_INPUT, storage.mountmgr_create_point_input, structs-mntmgr_24dea6c0-cfff-4f87-a8d3-c019aa5b46c3.xml"
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
req.typenames: MOUNTMGR_CREATE_POINT_INPUT, *PMOUNTMGR_CREATE_POINT_INPUT
f1_keywords:
 - _MOUNTMGR_CREATE_POINT_INPUT
 - mountmgr/_MOUNTMGR_CREATE_POINT_INPUT
 - PMOUNTMGR_CREATE_POINT_INPUT
 - mountmgr/PMOUNTMGR_CREATE_POINT_INPUT
 - MOUNTMGR_CREATE_POINT_INPUT
 - mountmgr/MOUNTMGR_CREATE_POINT_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountmgr.h
api_name:
 - _MOUNTMGR_CREATE_POINT_INPUT
 - PMOUNTMGR_CREATE_POINT_INPUT
 - MOUNTMGR_CREATE_POINT_INPUT
---

## -description

The **MOUNTMGR_CREATE_POINT_INPUT** structure is used by the mount manager to send a symbolic link name to a client that has requested symbolic link name by means of an [**IOCTL_MOUNTMGR_CREATE_POINT**](ni-mountmgr-ioctl_mountmgr_create_point.md) request.

## -struct-fields

### -field SymbolicLinkNameOffset

Contains an offset in bytes into the output buffer where the symbolic link name is located.

### -field SymbolicLinkNameLength

Contains the length in bytes of the symbolic link name stored in the output buffer.

### -field DeviceNameOffset

Contains an offset in bytes into the output buffer where the nonpersistent (target) device name is located.

### -field DeviceNameLength

Contains the length in bytes of the nonpersistent (target) device name.

## -remarks

The name given for purposes of identifying the volume can be of any type: a unique volume name, a symbolic link name, or a nonpersistent device name.

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**IOCTL_MOUNTMGR_CREATE_POINT**](ni-mountmgr-ioctl_mountmgr_create_point.md)
