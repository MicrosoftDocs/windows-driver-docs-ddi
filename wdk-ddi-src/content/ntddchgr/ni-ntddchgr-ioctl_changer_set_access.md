---
UID: NI:ntddchgr.IOCTL_CHANGER_SET_ACCESS
title: IOCTL_CHANGER_SET_ACCESS (ntddchgr.h)
description: Sets the state of the device's import/export port (IEport), door, or keypad.
old-location: storage\ioctl_changer_set_access.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_CHANGER_SET_ACCESS IOCTL"]
ms.keywords: IOCTL_CHANGER_SET_ACCESS, IOCTL_CHANGER_SET_ACCESS control, IOCTL_CHANGER_SET_ACCESS control code [Storage Devices], k307_08d52a8e-d7a0-42c6-92f9-c5099670473c.xml, ntddchgr/IOCTL_CHANGER_SET_ACCESS, storage.ioctl_changer_set_access
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
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
 - IOCTL_CHANGER_SET_ACCESS
 - ntddchgr/IOCTL_CHANGER_SET_ACCESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddchgr.h
api_name:
 - IOCTL_CHANGER_SET_ACCESS
---

# IOCTL_CHANGER_SET_ACCESS IOCTL


## -description

Sets the state of the device's import/export port (IEport), door, or keypad.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

       The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_set_access">CHANGER_SET_ACCESS</a> structure indicating the element and the operation to perform.

### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(CHANGER_SET_ACCESS).

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes set. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, or STATUS_INVALID_PARAMETER.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_set_access">CHANGER_SET_ACCESS</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changersetaccess">ChangerSetAccess</a>
