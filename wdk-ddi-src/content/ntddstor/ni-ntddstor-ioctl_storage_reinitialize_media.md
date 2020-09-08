---
UID: NI:ntddstor.IOCTL_STORAGE_REINITIALIZE_MEDIA
title: IOCTL_STORAGE_REINITIALIZE_MEDIA (ntddstor.h)
description: A driver can use the IOCTL_STORAGE_REINITIALIZE_MEDIA control code to reinitialize/erase a device.
old-location: storage\ioctl_storage_reinitialize_media.htm
tech.root: storage
ms.assetid: 4ECF51C3-D098-49E2-A675-78066A15C221
ms.date: 09/12/2018
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

A driver can use the **IOCTL_STORAGE_REINITIALIZE_MEDIA** control code to reinitialize/erase a device. The IOCTL offloads the erasure to the storage device; there is no guarantee as to the successful deletion or recoverability of the data of the storage device after the command completes.  This IOCTL is limited to data disks on devices in the desktop device family. In Windows Preinstallation Environment (WinPE), this IOCTL is supported for both boot and data disks.

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

The **Information** field is set to zero if the operation completes successfully; otherwise, it is set to a non-zero value.

## -remarks

Initial implementation requires no input and returns no output other than status. Callers should first call [FSCTL_LOCK_VOLUME](https://docs.microsoft.com/windows/win32/api/winioctl/ni-winioctl-fsctl_lock_volume) before calling this ioctl to flush out cached data in upper layers. No waiting of outstanding request completion is done before issuing the command to the device.

## -see-also

[_IO_STATUS_BLOCK structure](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block)

[How to Complete an IRP in a Dispatch Routine](https://docs.microsoft.com/windows-hardware/drivers/kernel/how-to-complete-an-irp-in-a-dispatch-routine)

