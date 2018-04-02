---
UID: NS:mountmgr._MOUNTDEV_NAME
title: "_MOUNTDEV_NAME"
author: windows-driver-content
description: The MOUNTDEV_NAME structure holds the name of a device.
old-location: storage\mountdev_name.htm
old-project: storage
ms.assetid: 26f5e98d-0709-403a-abcf-776c117d4f38
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMOUNTDEV_NAME, MOUNTDEV_NAME, MOUNTDEV_NAME structure [Storage Devices], PMOUNTDEV_NAME, PMOUNTDEV_NAME structure pointer [Storage Devices], _MOUNTDEV_NAME, mountmgr/MOUNTDEV_NAME, mountmgr/PMOUNTDEV_NAME, storage.mountdev_name, structs-mntmgr_b7eec4f5-e4fc-4931-82e5-c6ac5cd4b48f.xml"
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
-	MOUNTDEV_NAME
product: Windows
targetos: Windows
req.typenames: MOUNTDEV_NAME, *PMOUNTDEV_NAME
---

# _MOUNTDEV_NAME structure


## -description


The MOUNTDEV_NAME structure holds the name of a device. 


## -struct-fields




### -field NameLength

Contains the length of the name, in bytes. 


### -field Name

Contains a variable-sized array of wide characters that holds the name of the device mount point. The name may be a nonpersistent target name such as "\Device\HarddiskVolume1", a persistent symbolic link name such as a drive letter, "\DosDevices\D:", or a mount point such as "\DosDevices\E:\FilesysD\mnt". 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560434">IOCTL_MOUNTDEV_LINK_CREATED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560436">IOCTL_MOUNTDEV_LINK_DELETED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560437">IOCTL_MOUNTDEV_QUERY_DEVICE_NAME</a>
 

 

