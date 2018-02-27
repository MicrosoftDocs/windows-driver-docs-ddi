---
UID: NS:mountmgr._MOUNTMGR_DRIVE_LETTER_INFORMATION
title: "_MOUNTMGR_DRIVE_LETTER_INFORMATION"
author: windows-driver-content
description: The MOUNTMGR_DRIVE_LETTER_INFORMATION structure is used by the mount manager to furnish a drive letter to a client that has requested a driver letter by means of an IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request.
old-location: storage\mountmgr_drive_letter_information.htm
old-project: storage
ms.assetid: ad8dc740-c297-43e7-beb9-d93019955fd3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PMOUNTMGR_DRIVE_LETTER_INFORMATION, MOUNTMGR_DRIVE_LETTER_INFORMATION, MOUNTMGR_DRIVE_LETTER_INFORMATION structure [Storage Devices], PMOUNTMGR_DRIVE_LETTER_INFORMATION, PMOUNTMGR_DRIVE_LETTER_INFORMATION structure pointer [Storage Devices], _MOUNTMGR_DRIVE_LETTER_INFORMATION, mountmgr/MOUNTMGR_DRIVE_LETTER_INFORMATION, mountmgr/PMOUNTMGR_DRIVE_LETTER_INFORMATION, storage.mountmgr_drive_letter_information, structs-mntmgr_19ece61a-9dda-466c-a414-047d71beeb2c.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mountmgr.h
api_name:
-	MOUNTMGR_DRIVE_LETTER_INFORMATION
product: Windows
targetos: Windows
req.typenames: MOUNTMGR_DRIVE_LETTER_INFORMATION, *PMOUNTMGR_DRIVE_LETTER_INFORMATION
---

# _MOUNTMGR_DRIVE_LETTER_INFORMATION structure


## -description


The MOUNTMGR_DRIVE_LETTER_INFORMATION structure is used by the mount manager to furnish a drive letter to a client that has requested a driver letter by means of an <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_next_drive_letter.md">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a> request. 


## -syntax


````
typedef struct _MOUNTMGR_DRIVE_LETTER_INFORMATION {
  BOOLEAN DriveLetterWasAssigned;
  UCHAR   CurrentDriveLetter;
} MOUNTMGR_DRIVE_LETTER_INFORMATION, *PMOUNTMGR_DRIVE_LETTER_INFORMATION;
````


## -struct-fields




### -field DriveLetterWasAssigned

Indicates when <b>TRUE</b> that member <b>CurrentDriveLetter</b> contains a drive letter. When <b>FALSE</b>, a driver letter was not assigned to the device. 


### -field CurrentDriveLetter

Contains either an existing or a newly assigned drive letter in the form of a single ASCII character (for example, "D") if <b>DriveLetterWasAssigned</b> is <b>TRUE</b>. 


## -remarks



For a general discussion of the mount manager and how it communicates with its clients, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_next_drive_letter.md">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTMGR_DRIVE_LETTER_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

