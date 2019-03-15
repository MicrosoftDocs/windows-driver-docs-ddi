---
UID: NS:mountmgr._MOUNTMGR_DRIVE_LETTER_INFORMATION
title: _MOUNTMGR_DRIVE_LETTER_INFORMATION (mountmgr.h)
description: The MOUNTMGR_DRIVE_LETTER_INFORMATION structure is used by the mount manager to furnish a drive letter to a client that has requested a driver letter by means of an IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request.
old-location: storage\mountmgr_drive_letter_information.htm
tech.root: storage
ms.assetid: ad8dc740-c297-43e7-beb9-d93019955fd3
ms.date: 03/29/2018
ms.keywords: "*PMOUNTMGR_DRIVE_LETTER_INFORMATION, MOUNTMGR_DRIVE_LETTER_INFORMATION, MOUNTMGR_DRIVE_LETTER_INFORMATION structure [Storage Devices], PMOUNTMGR_DRIVE_LETTER_INFORMATION, PMOUNTMGR_DRIVE_LETTER_INFORMATION structure pointer [Storage Devices], _MOUNTMGR_DRIVE_LETTER_INFORMATION, mountmgr/MOUNTMGR_DRIVE_LETTER_INFORMATION, mountmgr/PMOUNTMGR_DRIVE_LETTER_INFORMATION, storage.mountmgr_drive_letter_information, structs-mntmgr_19ece61a-9dda-466c-a414-047d71beeb2c.xml"
ms.topic: struct
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
- MOUNTMGR_DRIVE_LETTER_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: MOUNTMGR_DRIVE_LETTER_INFORMATION, *PMOUNTMGR_DRIVE_LETTER_INFORMATION
---

# _MOUNTMGR_DRIVE_LETTER_INFORMATION structure


## -description


The MOUNTMGR_DRIVE_LETTER_INFORMATION structure is used by the mount manager to furnish a drive letter to a client that has requested a driver letter by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560473">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a> request. 


## -struct-fields




### -field DriveLetterWasAssigned

Indicates when <b>TRUE</b> that member <b>CurrentDriveLetter</b> contains a drive letter. When <b>FALSE</b>, a driver letter was not assigned to the device. 


### -field CurrentDriveLetter

Contains either an existing or a newly assigned drive letter in the form of a single ASCII character (for example, "D") if <b>DriveLetterWasAssigned</b> is <b>TRUE</b>. 


## -remarks



For a general discussion of the mount manager and how it communicates with its clients, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560473">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a>
 

 

