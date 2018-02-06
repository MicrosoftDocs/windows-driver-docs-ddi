---
UID: NS:mountmgr._MOUNTMGR_TARGET_NAME
title: "_MOUNTMGR_TARGET_NAME"
author: windows-driver-content
description: The MOUNTMGR_TARGET_NAME structure contains the nonpersistent target device name for a device and is used by mount manager clients with the IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE request to tell the mount manager to keep the symbolic link for a device active even after the device has gone offline.
old-location: storage\mountmgr_target_name.htm
old-project: storage
ms.assetid: 7a9cdc0d-0275-4ef9-a570-8788f77099af
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: MOUNTMGR_TARGET_NAME, MOUNTMGR_TARGET_NAME structure [Storage Devices], PMOUNTMGR_TARGET_NAME structure pointer [Storage Devices], PMOUNTMGR_TARGET_NAME, _MOUNTMGR_TARGET_NAME, mountmgr/PMOUNTMGR_TARGET_NAME, structs-mntmgr_abcf0a10-ecbb-433e-9848-c2d5065ca1ac.xml, storage.mountmgr_target_name, *PMOUNTMGR_TARGET_NAME, mountmgr/MOUNTMGR_TARGET_NAME
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
-	MOUNTMGR_TARGET_NAME
product: Windows
targetos: Windows
req.typenames: MOUNTMGR_TARGET_NAME, *PMOUNTMGR_TARGET_NAME
---

# _MOUNTMGR_TARGET_NAME structure


## -description


The MOUNTMGR_TARGET_NAME structure contains the nonpersistent target device name for a device and is used by mount manager clients with the  <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_keep_links_when_offline.md">IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE</a> request to tell the mount manager to keep the symbolic link for a device active even after the device has gone offline. 


## -syntax


````
typedef struct _MOUNTMGR_TARGET_NAME {
  USHORT DeviceNameLength;
  WCHAR  DeviceName[1];
} MOUNTMGR_TARGET_NAME, *PMOUNTMGR_TARGET_NAME;
````


## -struct-fields




### -field DeviceNameLength

Contains the length, in bytes, of the device name stored in <b>DeviceName</b>. 


### -field DeviceName

Contains the nonpersistent target device name. 


## -remarks


Nonpersistent target names must contain the full path of a target object name in the system object tree. For example: "\Device\HarddiskVolume1". For a discussion of the different between symbolic links, unique IDs, and nonpersistent device names, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 



## -see-also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_keep_links_when_offline.md">IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTMGR_TARGET_NAME structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

