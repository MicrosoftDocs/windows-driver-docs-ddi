---
UID: NS:mountmgr._MOUNTMGR_DRIVE_LETTER_INFORMATION
title: MOUNTMGR_DRIVE_LETTER_INFORMATION (mountmgr.h)
description: Learn about the MOUNTMGR_DRIVE_LETTER_INFORMATION structure.
tech.root: storage
ms.date: 06/04/2024
keywords: ["MOUNTMGR_DRIVE_LETTER_INFORMATION structure"]
ms.keywords: "*PMOUNTMGR_DRIVE_LETTER_INFORMATION, MOUNTMGR_DRIVE_LETTER_INFORMATION, MOUNTMGR_DRIVE_LETTER_INFORMATION structure [Storage Devices], PMOUNTMGR_DRIVE_LETTER_INFORMATION, PMOUNTMGR_DRIVE_LETTER_INFORMATION structure pointer [Storage Devices], _MOUNTMGR_DRIVE_LETTER_INFORMATION, mountmgr/MOUNTMGR_DRIVE_LETTER_INFORMATION, mountmgr/PMOUNTMGR_DRIVE_LETTER_INFORMATION, storage.mountmgr_drive_letter_information, structs-mntmgr_19ece61a-9dda-466c-a414-047d71beeb2c.xml"
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
req.typenames: MOUNTMGR_DRIVE_LETTER_INFORMATION, *PMOUNTMGR_DRIVE_LETTER_INFORMATION
f1_keywords:
 - _MOUNTMGR_DRIVE_LETTER_INFORMATION
 - mountmgr/_MOUNTMGR_DRIVE_LETTER_INFORMATION
 - PMOUNTMGR_DRIVE_LETTER_INFORMATION
 - mountmgr/PMOUNTMGR_DRIVE_LETTER_INFORMATION
 - MOUNTMGR_DRIVE_LETTER_INFORMATION
 - mountmgr/MOUNTMGR_DRIVE_LETTER_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountmgr.h
api_name:
 - _MOUNTMGR_DRIVE_LETTER_INFORMATION
 - PMOUNTMGR_DRIVE_LETTER_INFORMATION
 - MOUNTMGR_DRIVE_LETTER_INFORMATION
---

## -description

The **MOUNTMGR_DRIVE_LETTER_INFORMATION** structure is used by the mount manager to furnish a drive letter to a client that has requested a driver letter by means of an [**IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER**](ni-mountmgr-ioctl_mountmgr_next_drive_letter.md) request.

## -struct-fields

### -field DriveLetterWasAssigned

Indicates when TRUE that member **CurrentDriveLetter** contains a drive letter. When FALSE, a driver letter was not assigned to the device.

### -field CurrentDriveLetter

Contains either an existing or a newly assigned drive letter in the form of a single ASCII character (for example, "D") if **DriveLetterWasAssigned** is TRUE.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER**](ni-mountmgr-ioctl_mountmgr_next_drive_letter.md)
