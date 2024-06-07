---
UID: NS:mountmgr._MOUNTMGR_DRIVE_LETTER_TARGET
title: MOUNTMGR_DRIVE_LETTER_TARGET (mountmgr.h)
description: Learn about the MOUNTMGR_DRIVE_LETTER_TARGET structure.
tech.root: storage
ms.date: 06/04/2024
keywords: ["MOUNTMGR_DRIVE_LETTER_TARGET structure"]
ms.keywords: "*PMOUNTMGR_DRIVE_LETTER_TARGET, MOUNTMGR_DRIVE_LETTER_TARGET, MOUNTMGR_DRIVE_LETTER_TARGET structure [Storage Devices], PMOUNTMGR_DRIVE_LETTER_TARGET, PMOUNTMGR_DRIVE_LETTER_TARGET structure pointer [Storage Devices], _MOUNTMGR_DRIVE_LETTER_TARGET, mountmgr/MOUNTMGR_DRIVE_LETTER_TARGET, mountmgr/PMOUNTMGR_DRIVE_LETTER_TARGET, storage.mountmgr_drive_letter_target, structs-mntmgr_66751bbf-3c3a-407d-9faf-1ef190c9c7a2.xml"
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
req.typenames: MOUNTMGR_DRIVE_LETTER_TARGET, *PMOUNTMGR_DRIVE_LETTER_TARGET
f1_keywords:
 - _MOUNTMGR_DRIVE_LETTER_TARGET
 - mountmgr/_MOUNTMGR_DRIVE_LETTER_TARGET
 - PMOUNTMGR_DRIVE_LETTER_TARGET
 - mountmgr/PMOUNTMGR_DRIVE_LETTER_TARGET
 - MOUNTMGR_DRIVE_LETTER_TARGET
 - mountmgr/MOUNTMGR_DRIVE_LETTER_TARGET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountmgr.h
api_name:
 - _MOUNTMGR_DRIVE_LETTER_TARGET
 - PMOUNTMGR_DRIVE_LETTER_TARGET
 - MOUNTMGR_DRIVE_LETTER_TARGET
---

## -description

The **MOUNTMGR_DRIVE_LETTER_TARGET** structure is used by a mount manager client with an [**IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER**](ni-mountmgr-ioctl_mountmgr_next_drive_letter.md) request to furnish a nonpersistent target device name to the mount manager.

## -struct-fields

### -field DeviceNameLength

Contains the length, in bytes, of device name.

### -field DeviceName

Contains the nonpersistent target device name.

## -remarks

The mount manager responds to the IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request by furnishing the client with a drive letter for the target device.

Nonpersistent target names must contain the full path of a target object name in the system object tree. For example: "\Device\HarddiskVolume1".

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER**](ni-mountmgr-ioctl_mountmgr_next_drive_letter.md)
