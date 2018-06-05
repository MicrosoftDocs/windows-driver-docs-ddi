---
UID: NI:mountdev.IOCTL_MOUNTDEV_LINK_DELETED
title: IOCTL_MOUNTDEV_LINK_DELETED
author: windows-driver-content
description: Support for this IOCTL by the mount manager clients is optional. It alerts the mount manager client that a persistent name associated with it has been deleted. The input for this IOCTL is the persistent name that was deleted.
old-location: storage\ioctl_mountdev_link_deleted.htm
old-project: storage
ms.assetid: 6fd0696d-5b8d-4502-bbdb-a013bee2e9d4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_MOUNTDEV_LINK_DELETED, IOCTL_MOUNTDEV_LINK_DELETED control, IOCTL_MOUNTDEV_LINK_DELETED control code [Storage Devices], k307_b0ab5504-dac9-410f-bb73-bbb5876e4a59.xml, mountdev/IOCTL_MOUNTDEV_LINK_DELETED, storage.ioctl_mountdev_link_deleted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountdev.h
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
-	mountdev.h
api_name:
-	IOCTL_MOUNTDEV_LINK_DELETED
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_MOUNTDEV_LINK_DELETED IOCTL


## -description


Support for this IOCTL by the mount manager clients is optional. It alerts the mount manager client that a persistent name associated with it has been deleted. The input for this IOCTL is the persistent name that was deleted. 


## -ioctlparameters




### -input-buffer

The mount point manager places a variable-length structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff562256">MOUNTDEV_NAME</a>, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The mount manager inserts the persistent name just assigned at the address pointed to by the <i>Name</i> member of this structure. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTDEV_NAME).


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer








### -inout-buffer-length








### -status-block

No status.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562256">MOUNTDEV_NAME</a>
 

 

