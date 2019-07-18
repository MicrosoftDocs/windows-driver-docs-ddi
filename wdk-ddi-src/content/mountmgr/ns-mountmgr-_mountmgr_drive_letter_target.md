---
UID: NS:mountmgr._MOUNTMGR_DRIVE_LETTER_TARGET
title: _MOUNTMGR_DRIVE_LETTER_TARGET (mountmgr.h)
description: The MOUNTMGR_DRIVE_LETTER_TARGET structure is used by a mount manager client with an IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request to furnish a nonpersistent target device name to the mount manager.
old-location: storage\mountmgr_drive_letter_target.htm
tech.root: storage
ms.assetid: 3bbfd3f8-9530-4c9f-99e3-a1fcbb956b51
ms.date: 03/29/2018
ms.keywords: "*PMOUNTMGR_DRIVE_LETTER_TARGET, MOUNTMGR_DRIVE_LETTER_TARGET, MOUNTMGR_DRIVE_LETTER_TARGET structure [Storage Devices], PMOUNTMGR_DRIVE_LETTER_TARGET, PMOUNTMGR_DRIVE_LETTER_TARGET structure pointer [Storage Devices], _MOUNTMGR_DRIVE_LETTER_TARGET, mountmgr/MOUNTMGR_DRIVE_LETTER_TARGET, mountmgr/PMOUNTMGR_DRIVE_LETTER_TARGET, storage.mountmgr_drive_letter_target, structs-mntmgr_66751bbf-3c3a-407d-9faf-1ef190c9c7a2.xml"
ms.topic: struct
f1_keywords:
 - "mountmgr/MOUNTMGR_DRIVE_LETTER_TARGET"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mountmgr.h
api_name:
- MOUNTMGR_DRIVE_LETTER_TARGET
product:
- Windows
targetos: Windows
req.typenames: MOUNTMGR_DRIVE_LETTER_TARGET, *PMOUNTMGR_DRIVE_LETTER_TARGET
---

# _MOUNTMGR_DRIVE_LETTER_TARGET structure


## -description


The MOUNTMGR_DRIVE_LETTER_TARGET structure is used by a mount manager client with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mountmgr/ni-mountmgr-ioctl_mountmgr_next_drive_letter">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a> request to furnish a nonpersistent target device name to the mount manager. 


## -struct-fields




### -field DeviceNameLength

Contains the length, in bytes, of device name. 


### -field DeviceName

Contains the nonpersistent target device name. 


## -remarks



The mount manager responds to the IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request by furnishing the client with a drive letter for the target device. 

Nonpersistent target names must contain the full path of a target object name in the system object tree. For example: "\Device\HarddiskVolume1". For a discussion of the difference between drive letters and nonpersistent target device names, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mountmgr/ni-mountmgr-ioctl_mountmgr_next_drive_letter">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a>
 

 

