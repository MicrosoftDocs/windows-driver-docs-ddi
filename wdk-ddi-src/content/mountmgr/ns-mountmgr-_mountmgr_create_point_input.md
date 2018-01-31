---
UID: NS:mountmgr._MOUNTMGR_CREATE_POINT_INPUT
title: "_MOUNTMGR_CREATE_POINT_INPUT"
author: windows-driver-content
description: The MOUNTMGR_CREATE_POINT_INPUT structure is used by the mount manager to send a symbolic link name to a client that has requested symbolic link name by means of an IOCTL_MOUNTMGR_CREATE_POINT request.
old-location: storage\mountmgr_create_point_input.htm
old-project: storage
ms.assetid: b53d5163-612d-4bfb-89f4-21457629e365
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: mountmgr/MOUNTMGR_CREATE_POINT_INPUT, PMOUNTMGR_CREATE_POINT_INPUT structure pointer [Storage Devices], mountmgr/PMOUNTMGR_CREATE_POINT_INPUT, structs-mntmgr_24dea6c0-cfff-4f87-a8d3-c019aa5b46c3.xml, _MOUNTMGR_CREATE_POINT_INPUT, MOUNTMGR_CREATE_POINT_INPUT structure [Storage Devices], storage.mountmgr_create_point_input, PMOUNTMGR_CREATE_POINT_INPUT, *PMOUNTMGR_CREATE_POINT_INPUT, MOUNTMGR_CREATE_POINT_INPUT
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
-	MOUNTMGR_CREATE_POINT_INPUT
product: Windows
targetos: Windows
req.typenames: "*PMOUNTMGR_CREATE_POINT_INPUT, MOUNTMGR_CREATE_POINT_INPUT"
---

# _MOUNTMGR_CREATE_POINT_INPUT structure


## -description


The MOUNTMGR_CREATE_POINT_INPUT structure is used by the mount manager to send a symbolic link name to a client that has requested symbolic link name by means of an <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_create_point.md">IOCTL_MOUNTMGR_CREATE_POINT</a> request. 


## -syntax


````
typedef struct _MOUNTMGR_CREATE_POINT_INPUT {
  USHORT SymbolicLinkNameOffset;
  USHORT SymbolicLinkNameLength;
  USHORT DeviceNameOffset;
  USHORT DeviceNameLength;
} MOUNTMGR_CREATE_POINT_INPUT, *PMOUNTMGR_CREATE_POINT_INPUT;
````


## -struct-fields




#### - SymbolicLinkNameOffset

Contains an offset in bytes into the output buffer where the symbolic link name is located. 


#### - SymbolicLinkNameLength

Contains the length in bytes of the symbolic link name stored in the output buffer. 


#### - DeviceNameOffset

Contains an offset in bytes into the output buffer where the nonpersistent (target) device name is located. 


#### - DeviceNameLength

Contains the length in bytes of the nonpersistent (target) device name. 


## -remarks


The name given for purposes of identifying the volume can be of any type: a unique volume name, a symbolic link name, or a nonpersistent device name. For a discussion of the difference between symbolic link names and nonpersistent target device names, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 



## -see-also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_create_point.md">IOCTL_MOUNTMGR_CREATE_POINT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTMGR_CREATE_POINT_INPUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

