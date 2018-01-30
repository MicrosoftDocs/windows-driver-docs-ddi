---
UID: NS:mountmgr._MOUNTMGR_DRIVE_LETTER_TARGET
title: "_MOUNTMGR_DRIVE_LETTER_TARGET"
author: windows-driver-content
description: The MOUNTMGR_DRIVE_LETTER_TARGET structure is used by a mount manager client with an IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request to furnish a nonpersistent target device name to the mount manager.
old-location: storage\mountmgr_drive_letter_target.htm
old-project: storage
ms.assetid: 3bbfd3f8-9530-4c9f-99e3-a1fcbb956b51
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: MOUNTMGR_DRIVE_LETTER_TARGET, *PMOUNTMGR_DRIVE_LETTER_TARGET, _MOUNTMGR_DRIVE_LETTER_TARGET, mountmgr/MOUNTMGR_DRIVE_LETTER_TARGET, PMOUNTMGR_DRIVE_LETTER_TARGET, MOUNTMGR_DRIVE_LETTER_TARGET structure [Storage Devices], structs-mntmgr_66751bbf-3c3a-407d-9faf-1ef190c9c7a2.xml, PMOUNTMGR_DRIVE_LETTER_TARGET structure pointer [Storage Devices], mountmgr/PMOUNTMGR_DRIVE_LETTER_TARGET, storage.mountmgr_drive_letter_target
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mountmgr.h
apiname:
-	MOUNTMGR_DRIVE_LETTER_TARGET
product: Windows
targetos: Windows
req.typenames: "*PMOUNTMGR_DRIVE_LETTER_TARGET, MOUNTMGR_DRIVE_LETTER_TARGET"
---

# _MOUNTMGR_DRIVE_LETTER_TARGET structure


## -description


The MOUNTMGR_DRIVE_LETTER_TARGET structure is used by a mount manager client with an <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_next_drive_letter.md">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a> request to furnish a nonpersistent target device name to the mount manager. 


## -syntax


````
typedef struct _MOUNTMGR_DRIVE_LETTER_TARGET {
  USHORT DeviceNameLength;
  WCHAR  DeviceName[1];
} MOUNTMGR_DRIVE_LETTER_TARGET, *PMOUNTMGR_DRIVE_LETTER_TARGET;
````


## -struct-fields




### -field DeviceNameLength

Contains the length, in bytes, of device name. 


### -field DeviceName

Contains the nonpersistent target device name. 


## -remarks


The mount manager responds to the IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request by furnishing the client with a drive letter for the target device. 

Nonpersistent target names must contain the full path of a target object name in the system object tree. For example: "\Device\HarddiskVolume1". For a discussion of the difference between drive letters and nonpersistent target device names, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 



## -see-also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_next_drive_letter.md">IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTMGR_DRIVE_LETTER_TARGET structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

