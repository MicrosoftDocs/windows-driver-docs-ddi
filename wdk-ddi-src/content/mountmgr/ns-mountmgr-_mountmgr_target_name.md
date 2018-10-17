---
UID: NS:mountmgr._MOUNTMGR_TARGET_NAME
title: "_MOUNTMGR_TARGET_NAME"
author: windows-driver-content
description: The MOUNTMGR_TARGET_NAME structure contains the nonpersistent target device name for a device and is used by mount manager clients with the IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE request to tell the mount manager to keep the symbolic link for a device active even after the device has gone offline.
old-location: storage\mountmgr_target_name.htm
tech.root: storage
ms.assetid: 7a9cdc0d-0275-4ef9-a570-8788f77099af
ms.date: 3/29/2018
ms.keywords: "*PMOUNTMGR_TARGET_NAME, MOUNTMGR_TARGET_NAME, MOUNTMGR_TARGET_NAME structure [Storage Devices], PMOUNTMGR_TARGET_NAME, PMOUNTMGR_TARGET_NAME structure pointer [Storage Devices], _MOUNTMGR_TARGET_NAME, mountmgr/MOUNTMGR_TARGET_NAME, mountmgr/PMOUNTMGR_TARGET_NAME, storage.mountmgr_target_name, structs-mntmgr_abcf0a10-ecbb-433e-9848-c2d5065ca1ac.xml"
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
-	MOUNTMGR_TARGET_NAME
product:
- Windows
targetos: Windows
req.typenames: MOUNTMGR_TARGET_NAME, *PMOUNTMGR_TARGET_NAME
---

# _MOUNTMGR_TARGET_NAME structure


## -description


The MOUNTMGR_TARGET_NAME structure contains the nonpersistent target device name for a device and is used by mount manager clients with the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560468">IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE</a> request to tell the mount manager to keep the symbolic link for a device active even after the device has gone offline. 


## -struct-fields




### -field DeviceNameLength

Contains the length, in bytes, of the device name stored in <b>DeviceName</b>. 


### -field DeviceName

Contains the nonpersistent target device name. 


## -remarks



Nonpersistent target names must contain the full path of a target object name in the system object tree. For example: "\Device\HarddiskVolume1". For a discussion of the different between symbolic links, unique IDs, and nonpersistent device names, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560468">IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE</a>
 

 

