---
UID: NI:mountmgr.IOCTL_MOUNTMGR_CHANGE_NOTIFY
title: IOCTL_MOUNTMGR_CHANGE_NOTIFY (mountmgr.h)
description: Learn about the IOCTL_MOUNTMGR_CHANGE_NOTIFY IOCTL.
tech.root: storage
ms.date: 06/04/2024
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

## -description

Clients send this IOCTL to the mount manager to be informed whenever there is a change in the mount manager's persistent symbolic link name database.

The mount manager maintains a counter called **EpicNumber** that records how many changes have occurred in its persistent name database since the last startup. Clients send a number to the mount manager with every change notification request IRP, and the mount manager responds in the following manner:

* If the number supplied by the client is not equal to **EpicNumber**, the mount manager returns STATUS_SUCCESS, indicating that changes have occurred since the client last compared its number with the mount manager's **EpicNumber**.

* If the number supplied by the client is equal to **EpicNumber**, the mount manager interprets this as a request to be informed of the next change to the persistent name database, and it queues the change notification IRP and returns STATUS_PENDING. Whenever a change occurs in the database, the mount manager completes all of the pending change notification IRPs, thereby informing clients of the change.

A client that only wants to be informed of the changes to a particular volume is advised to register for Plug and Play target device notification and watch for GUID_IO_VOLUME_NAME_CHANGE.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

The mount manager client initializes the [**MOUNTMGR_CHANGE_NOTIFY_INFO**](ns-mountmgr-_mountmgr_change_notify_info.md) structure at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to ```sizeof(MOUNTMGR_CHANGE_NOTIFY_INFO)```.

### -output-buffer

The mount manager returns the current **EpicNumber** in the [**MOUNTMGR_CHANGE_NOTIFY_INFO**](ns-mountmgr-_mountmgr_change_notify_info.md) structure at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

None.

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

If the operation is successful, the **Status** field is set to STATUS_SUCCESS and the **Information** field is set to ```sizeof(MOUNTMGR_CHANGE_NOTIFY_INFO)```.

If **InputBufferLength** is less than ```sizeof(MOUNTMGR_CHANGE_NOTIFY_INFO)``` or **OutputBufferLength** is less than ```sizeof(MOUNTMGR_CHANGE_NOTIFY_INFO)```, the **Status** field is set to STATUS_INVALID_PARAMETER.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**MOUNTMGR_CHANGE_NOTIFY_INFO**](ns-mountmgr-_mountmgr_change_notify_info.md)
