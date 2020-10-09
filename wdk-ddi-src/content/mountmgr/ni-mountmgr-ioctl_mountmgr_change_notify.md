---
UID: NI:mountmgr.IOCTL_MOUNTMGR_CHANGE_NOTIFY
title: IOCTL_MOUNTMGR_CHANGE_NOTIFY (mountmgr.h)
description: Clients send this IOCTL to the mount manager to be informed whenever there is a change in the mount manager's persistent symbolic link name database.
old-location: storage\ioctl_mountmgr_change_notify.htm
tech.root: storage
ms.assetid: ad6ab15b-6789-4ee8-ba99-9eaa6eec070a
ms.date: 03/29/2018
keywords: ["IOCTL_MOUNTMGR_CHANGE_NOTIFY IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_CHANGE_NOTIFY, IOCTL_MOUNTMGR_CHANGE_NOTIFY control, IOCTL_MOUNTMGR_CHANGE_NOTIFY control code [Storage Devices], k307_009033eb-e845-4967-9ef1-30f11bfa3253.xml, mountmgr/IOCTL_MOUNTMGR_CHANGE_NOTIFY, storage.ioctl_mountmgr_change_notify
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_MOUNTMGR_CHANGE_NOTIFY
 - mountmgr/IOCTL_MOUNTMGR_CHANGE_NOTIFY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_CHANGE_NOTIFY
---

# IOCTL_MOUNTMGR_CHANGE_NOTIFY IOCTL


## -description

Clients send this IOCTL to the mount manager to be informed whenever there is a change in the mount manager's persistent symbolic link name database. 

The mount manager maintains a counter called <i>EpicNumber</i> that records how many changes have occurred in its persistent name database since the last startup. Clients send a number to the mount manager with every change notification request IRP, and the mount manager responds in the following manner:
<ul>
<li>
If the number supplied by the client is not equal to <i>EpicNumber</i>, the mount manager returns STATUS_SUCCESS, indicating that changes have occurred since the client last compared its number with the mount manager's <i>EpicNumber</i>. 

</li>
<li>
If the number supplied by the client is equal to <i>EpicNumber</i>, the mount manager interprets this as a request to be informed of the next change to the persistent name database, and it queues the change notification IRP and returns STATUS_PENDING. Whenever a change occurs in the database, the mount manager completes all of the pending change notification IRPs, thereby informing clients of the change.

</li>
</ul>A client that only wants to be informed of the changes to a particular volume is advised to register for Plug and Play target device notification and watch for GUID_IO_VOLUME_NAME_CHANGE.

## -ioctlparameters

### -input-buffer

The mount manager client initializes the <a href="/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_change_notify_info">MOUNTMGR_CHANGE_NOTIFY_INFO</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_CHANGE_NOTIFY_INFO).

### -output-buffer

The mount manager returns the current <i>EpicNumber</i> in the <a href="/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_change_notify_info">MOUNTMGR_CHANGE_NOTIFY_INFO</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS and the <b>Information</b> field is set to <b>sizeof</b>(MOUNTMGR_CHANGE_NOTIFY_INFO).

If <b>InputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_CHANGE_NOTIFY_INFO) or <b>OutputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_CHANGE_NOTIFY_INFO), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

## -see-also

<a href="/windows-hardware/drivers/ddi/mountmgr/ns-mountmgr-_mountmgr_change_notify_info">MOUNTMGR_CHANGE_NOTIFY_INFO</a>