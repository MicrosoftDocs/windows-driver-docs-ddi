---
UID: NI:ntddstor.IOCTL_STORAGE_REINITIALIZE_MEDIA
title: IOCTL_STORAGE_REINITIALIZE_MEDIA (ntddstor.h)
description: A driver can use the IOCTL_STORAGE_REINITIALIZE_MEDIA control code to reinitialize/erase a device.
old-location: storage\ioctl_storage_reinitialize_media.htm
tech.root: storage
ms.date: 05/13/2021
keywords: ["IOCTL_STORAGE_REINITIALIZE_MEDIA IOCTL"]
ms.keywords: IOCTL_STORAGE_REINITIALIZE_MEDIA, IOCTL_STORAGE_REINITIALIZE_MEDIA control, IOCTL_STORAGE_REINITIALIZE_MEDIA control code [Storage Devices], ntddstor/IOCTL_STORAGE_REINITIALIZE_MEDIA, storage.ioctl_storage_reinitialize_media
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
 - IOCTL_STORAGE_REINITIALIZE_MEDIA
 - ntddstor/IOCTL_STORAGE_REINITIALIZE_MEDIA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_REINITIALIZE_MEDIA
---

# IOCTL_STORAGE_REINITIALIZE_MEDIA IOCTL

## -description

A driver can issue a **IOCTL_STORAGE_REINITIALIZE_MEDIA** control code to offload the erasure process to the storage device.

## -ioctlparameters

### -input-buffer

For Windows Server 2022 and later, contains an optional [**STORAGE_REINITIALIZE_MEDIA**](ns-ntddstor-storage_reinitialize_media.md) structure with sanitize options, or NULL. For earlier OS versions, the input buffer is NULL.

### -input-buffer-length

For Windows 10 release 21H1 and later, **Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= sizeof(STORAGE_REINITIALIZE_MEDIA) if **Parameters.DeviceIoControl.InputBuffer** != NULL; otherwise zero. For earlier OS versions, the input buffer length is zero.

### -output-buffer

None.

### -output-buffer-length

None.

### -status-block

The **Information** field is set to zero if the call completes successfully; otherwise, it is set to a non-zero value.

## -remarks

 **IOCTL_STORAGE_REINITIALIZE_MEDIA** offloads the erasure to the storage device. There is no guarantee as to the successful deletion or recoverability of the data of the storage device after the command completes.

This IOCTL is limited to data disks on devices in the desktop device family. In Windows Preinstallation Environment (WinPE), this IOCTL is supported for both boot and data disks.

In earlier OS versions, the implementation requires no input and returns no output other than status.

Callers should first call [FSCTL_LOCK_VOLUME](/windows/win32/api/winioctl/ni-winioctl-fsctl_lock_volume) before calling this IOCTL to flush out cached data in upper layers. No waiting of outstanding request completion is done before issuing the command to the device.

## -see-also

[IO_STATUS_BLOCK structure](../wdm/ns-wdm-_io_status_block.md)

[**STORAGE_REINITIALIZE_MEDIA**](ns-ntddstor-storage_reinitialize_media.md)

[How to Complete an IRP in a Dispatch Routine](/windows-hardware/drivers/kernel/how-to-complete-an-irp-in-a-dispatch-routine)
