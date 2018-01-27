---
UID: NI:mountmgr.IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
title: IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
author: windows-driver-content
description: This IOCTL directs the mount manager to keep a symbolic link active after the Plug and Play manager has given notification that its corresponding volume has gone offline.
old-location: storage\ioctl_mountmgr_keep_links_when_offline.htm
old-project: storage
ms.assetid: 56af77f9-7c29-4bde-a8ae-9af23af4d296
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_mountmgr_keep_links_when_offline, IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE control code [Storage Devices], IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE, mountmgr/IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE, k307_7502107c-0301-45d9-a0b6-8aa6e9e231c9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	Mountmgr.h
apiname: 
-	IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE
product: Windows
targetos: Windows
req.typenames: MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
---

# IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


This IOCTL directs the mount manager to keep a symbolic link active after the Plug and Play manager has given notification that its corresponding volume has gone offline. When the volume goes back online, the mount manager reassigns the symbolic link to the volume. No other volume is allowed to claim the symbolic link while its original owner is offline.

Clusters use this IOCTL to ensure that a node can continue to access a volume with the same drive letter, even if the volume is not continually present in the system.


## -ioctlparameters




### -input-buffer

The mount manager client loads the following structure with the symbolic link that will persist even after its volume is removed from the system. The initialized structure <a href="..\mountmgr\ns-mountmgr-_mountmgr_target_name.md">MOUNTMGR_TARGET_NAME</a>, defined in <i>Mountmgr.h</i>, is inserted at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_TARGET_NAME).


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

The input buffer size, indicated by <b>InputBufferLength</b>, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.


## -see-also

<a href="..\mountmgr\ns-mountmgr-_mountmgr_target_name.md">MOUNTMGR_TARGET_NAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

