---
UID: NI:mountmgr.IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
title: IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
author: windows-driver-content
description: This IOCTL allows a client to simulate a Plug and Play device interface arrival notification with the given volume name.
old-location: storage\ioctl_mountmgr_volume_arrival_notification.htm
old-project: storage
ms.assetid: 0c27c49e-a06c-4781-9d7f-50f15f9715ac
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION, IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION control code [Storage Devices], k307_7a15b0f1-9be7-476f-936c-225e39ef53c0.xml, mountmgr/IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION, storage.ioctl_mountmgr_volume_arrival_notification
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Mountmgr.h
api_name:
-	IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
---

# IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION IOCTL


## -description


This IOCTL allows a client to simulate a Plug and Play device interface arrival notification with the given volume name. If a client does not register a device interface of type MOUNTDEV_MOUNTED_DEVICE_GUID, the mount manager is not alerted of its arrival. However, the client can alert the mount manager of its volume's arrival directly by means of this IOCTL.

This IOCTL allows clients to obtain drive letters for newly created volumes during text mode setup when the Plug and Play device installer is not running.

Clients that have registered a device interface of type MOUNTDEV_MOUNTED_DEVICE_GUID in the normal way should not use this IOCTL. 


## -ioctlparameters




### -input-buffer

The mount manager client loads the following structure with the nonpersistent target device name. The initialized structure, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562289">MOUNTMGR_TARGET_NAME</a>, defined in <i>Mountmgr.h</i>, is inserted at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562289">MOUNTMGR_TARGET_NAME</a>
 

 

