---
UID: NI:ntddvol.IOCTL_VOLUME_ONLINE
title: IOCTL_VOLUME_ONLINE (ntddvol.h)
description: The IOCTL_VOLUME_ONLINE IOCTL puts the volume in an ONLINE state, which is a state where read and write operations will be executed.
old-location: storage\ioctl_volume_online.htm
tech.root: storage
ms.assetid: 3391bda9-2eec-4c03-84ed-76b89e2c0cf0
ms.date: 03/29/2018
ms.keywords: IOCTL_VOLUME_ONLINE, IOCTL_VOLUME_ONLINE control, IOCTL_VOLUME_ONLINE control code [Storage Devices], k307_236159f9-4ec2-4dec-9d34-5b4ecb8a2147.xml, ntddvol/IOCTL_VOLUME_ONLINE, storage.ioctl_volume_online
ms.topic: ioctl
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
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
- Ntddvol.h
api_name:
- IOCTL_VOLUME_ONLINE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VOLUME_ONLINE IOCTL


## -description



The <b>IOCTL_VOLUME_ONLINE</b> IOCTL puts the volume in an ONLINE state, which is a state where read and write operations will be executed. The requests are passed down to the physical disk until a subsequent <a href="https://msdn.microsoft.com/library/windows/hardware/ff561431">IOCTL_VOLUME_OFFLINE</a> is received.

A common use for <b>IOCTL_VOLUME_ONLINE</b> is a case in which the mount manager automatically puts a new volume in the ONLINE state when the volume arrives, unless that volume is listed in a registry key that is populated by the cluster service. <b>IOCTL_VOLUME_ONLINE</b> is called for removable drives regardless of the NoAutoMount setting in the following registry key:

HKCU\System\CurrentControlSet\Services\Mountmgr\NoAutoMount

But for volumes controlled by NoAutoMount, assigning a drive letter will cause <b>IOCTL_VOLUME_ONLINE</b> to be called.

For volumes that are controlled by the cluster service, <b>IOCTL_VOLUME_ONLINE</b> is sent by the cluster service when the local node owns the volume. The cluster service uses both <b>IOCTL_VOLUME_ONLINE</b> and <b>IOCTL_VOLUME_ONLINE</b> to allow I/O to a disk volume when the disk volume is owned by the local server. Until the cluster service puts the disk volume in an ONLINE state, no I/O is permitted to the disk volume. This prevents disk volume corruption that could result from multiple cluster nodes writing to the same disk volume simultaneously.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> member is set to STATUS_SUCCESS.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561431">IOCTL_VOLUME_OFFLINE</a>
 

 

