---
UID: NI:mountmgr.IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
title: IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE (mountmgr.h)
description: This IOCTL directs the mount manager to keep a symbolic link active after the Plug and Play manager has given notification that its corresponding volume has gone offline.
old-location: storage\ioctl_mountmgr_keep_links_when_offline.htm
tech.root: storage
ms.assetid: 56af77f9-7c29-4bde-a8ae-9af23af4d296
ms.date: 03/29/2018
keywords: ["IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE, IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE control, IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE control code [Storage Devices], k307_7502107c-0301-45d9-a0b6-8aa6e9e231c9.xml, mountmgr/IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE, storage.ioctl_mountmgr_keep_links_when_offline
f1_keywords:
 - "mountmgr/IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE"
 - "IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Mountmgr.h
api_name:
- IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
targetos: Windows
req.typenames: 
---

# IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE IOCTL


## -description


This IOCTL directs the mount manager to keep a symbolic link active after the Plug and Play manager has given notification that its corresponding volume has gone offline. When the volume goes back online, the mount manager reassigns the symbolic link to the volume. No other volume is allowed to claim the symbolic link while its original owner is offline.

Clusters use this IOCTL to ensure that a node can continue to access a volume with the same drive letter, even if the volume is not continually present in the system.


## -ioctlparameters




### -input-buffer

The mount manager client loads the following structure with the symbolic link that will persist even after its volume is removed from the system. The initialized structure <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_target_name">MOUNTMGR_TARGET_NAME</a>, defined in <i>Mountmgr.h</i>, is inserted at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_TARGET_NAME).


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_target_name">MOUNTMGR_TARGET_NAME</a>
 

 

