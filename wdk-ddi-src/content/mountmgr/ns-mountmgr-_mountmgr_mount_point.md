---
UID: NS:mountmgr._MOUNTMGR_MOUNT_POINT
title: "_MOUNTMGR_MOUNT_POINT"
description: The MOUNTMGR_MOUNT_POINT structure is used by mount manager clients in conjunction with an IOCTL_MOUNTMGR_QUERY_POINTS request to query the mount manager for all of the mount points (symbolic links) associated with a device.
old-location: storage\mountmgr_mount_point.htm
tech.root: storage
ms.assetid: a4142380-1596-49dc-a18d-ac5c3cef73fe
ms.date: 03/29/2018
ms.keywords: "*PMOUNTMGR_MOUNT_POINT, MOUNTMGR_MOUNT_POINT, MOUNTMGR_MOUNT_POINT structure [Storage Devices], PMOUNTMGR_MOUNT_POINT, PMOUNTMGR_MOUNT_POINT structure pointer [Storage Devices], _MOUNTMGR_MOUNT_POINT, mountmgr/MOUNTMGR_MOUNT_POINT, mountmgr/PMOUNTMGR_MOUNT_POINT, storage.mountmgr_mount_point, structs-mntmgr_88136173-0786-4d4e-80b7-77f523e8d125.xml"
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
-	MOUNTMGR_MOUNT_POINT
product:
- Windows
targetos: Windows
req.typenames: MOUNTMGR_MOUNT_POINT, *PMOUNTMGR_MOUNT_POINT
---

# _MOUNTMGR_MOUNT_POINT structure


## -description


The MOUNTMGR_MOUNT_POINT structure is used by mount manager clients in conjunction with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a> request to query the mount manager for all of the mount points (symbolic links) associated with a device. The mount manager responds by sending an array of MOUNTMGR_MOUNT_POINT structures containing the mount points. 


## -struct-fields




### -field SymbolicLinkNameOffset

Contains an offset, in bytes, into the output buffer where the symbolic link is located.


### -field SymbolicLinkNameLength

Contains the length, in bytes, of the symbolic link. 


### -field Reserved1

 


### -field UniqueIdOffset

Contains an offset, in bytes, into the output buffer where the unique ID is located. 


### -field UniqueIdLength

Contains the length, in bytes, of the unique ID. 


### -field Reserved2

 


### -field DeviceNameOffset

Contains an offset, in bytes, into the output buffer where the nonpersistent device name is located. 


### -field DeviceNameLength

Contains the length, in bytes, of the nonpersistent device name. 


### -field Reserved3

 




## -remarks



None of the names returned are <b>NULL</b> terminated, nor do the buffers require terminating <b>NULL</b> characters. The caller of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a> is not required to provide data in all of the members of the MOUNTMGR_MOUNT_POINT structure, but empty members must have an offset of zero.

On input, offsets are from the beginning of the MOUNTMGR_MOUNT_POINT structure. On output offsets are from the beginning of the buffer. This is usually the same as the beginning of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562288">MOUNTMGR_MOUNT_POINTS</a> container structure (as opposed to the embedded MOUNTMGR_MOUNT_POINT array instance).

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a> request is available in Windows 2000 and later operating systems.

For a discussion of the different between symbolic links, unique IDs, and nonpersistent device names, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560474">IOCTL_MOUNTMGR_QUERY_POINTS</a>
 

 

