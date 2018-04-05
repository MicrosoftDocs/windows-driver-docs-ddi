---
UID: NS:mountmgr._MOUNTMGR_CREATE_POINT_INPUT
title: "_MOUNTMGR_CREATE_POINT_INPUT"
author: windows-driver-content
description: The MOUNTMGR_CREATE_POINT_INPUT structure is used by the mount manager to send a symbolic link name to a client that has requested symbolic link name by means of an IOCTL_MOUNTMGR_CREATE_POINT request.
old-location: storage\mountmgr_create_point_input.htm
old-project: storage
ms.assetid: b53d5163-612d-4bfb-89f4-21457629e365
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMOUNTMGR_CREATE_POINT_INPUT, MOUNTMGR_CREATE_POINT_INPUT, MOUNTMGR_CREATE_POINT_INPUT structure [Storage Devices], PMOUNTMGR_CREATE_POINT_INPUT, PMOUNTMGR_CREATE_POINT_INPUT structure pointer [Storage Devices], _MOUNTMGR_CREATE_POINT_INPUT, mountmgr/MOUNTMGR_CREATE_POINT_INPUT, mountmgr/PMOUNTMGR_CREATE_POINT_INPUT, storage.mountmgr_create_point_input, structs-mntmgr_24dea6c0-cfff-4f87-a8d3-c019aa5b46c3.xml"
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
-	MOUNTMGR_CREATE_POINT_INPUT
product:
- Windows
targetos: Windows
req.typenames: MOUNTMGR_CREATE_POINT_INPUT, *PMOUNTMGR_CREATE_POINT_INPUT
---

# _MOUNTMGR_CREATE_POINT_INPUT structure


## -description


The MOUNTMGR_CREATE_POINT_INPUT structure is used by the mount manager to send a symbolic link name to a client that has requested symbolic link name by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560457">IOCTL_MOUNTMGR_CREATE_POINT</a> request. 


## -struct-fields




### -field SymbolicLinkNameOffset

Contains an offset in bytes into the output buffer where the symbolic link name is located. 


### -field SymbolicLinkNameLength

Contains the length in bytes of the symbolic link name stored in the output buffer. 


### -field DeviceNameOffset

Contains an offset in bytes into the output buffer where the nonpersistent (target) device name is located. 


### -field DeviceNameLength

Contains the length in bytes of the nonpersistent (target) device name. 


## -remarks



The name given for purposes of identifying the volume can be of any type: a unique volume name, a symbolic link name, or a nonpersistent device name. For a discussion of the difference between symbolic link names and nonpersistent target device names, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560457">IOCTL_MOUNTMGR_CREATE_POINT</a>
 

 

