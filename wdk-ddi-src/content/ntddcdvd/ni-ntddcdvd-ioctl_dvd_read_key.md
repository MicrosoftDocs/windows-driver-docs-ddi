---
UID: NI:ntddcdvd.IOCTL_DVD_READ_KEY
title: IOCTL_DVD_READ_KEY (ntddcdvd.h)
description: Returns a copy-protection key of the specified type:\_challenge key, bus key, title key, read RPC key, set RPC key, or disk key.
old-location: storage\ioctl_dvd_read_key.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_DVD_READ_KEY IOCTL"]
ms.keywords: IOCTL_DVD_READ_KEY, IOCTL_DVD_READ_KEY control, IOCTL_DVD_READ_KEY control code [Storage Devices], k307_6baca45d-504c-46b9-9724-f82132c2bead.xml, ntddcdvd/IOCTL_DVD_READ_KEY, storage.ioctl_dvd_read_key
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
 - IOCTL_DVD_READ_KEY
 - ntddcdvd/IOCTL_DVD_READ_KEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_DVD_READ_KEY
---

# IOCTL_DVD_READ_KEY IOCTL


## -description

Returns a copy-protection key of the specified type: challenge key, bus key, title key, read RPC key, set RPC key, or disk key. A challenge key or bus key is sent back to the device to complete the related step in a DVD authentication sequence. After the authentication sequence is completed, a title key is used to encrypt and decrypt user data transferred from a DVD disc and a disk key is used to encrypt and decrypt title key data. If the drive region has not been set previously (if it is still at factory default) and if the inserted media has a region, the device region will be set to the current media region.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_copy_protect_key">DVD_COPY_PROTECT_KEY</a> structure that indicates the session ID of the DVD session and the type of key to return.

### -input-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the buffer, which must be >= the size of one of the following: DVD_CHALLENGE_KEY_LENGTH, DVD_BUS_KEY_LENGTH, DVD_TITLE_KEY_LENGTH, DVD_RPC_KEY_LENGTH, DVD_SET_RPC_KEY_LENGTH, or DVD_DISK_KEY_LENGTH.

### -output-buffer

The driver returns the DVD_COPY_PROTECT_KEY data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

Length of a <a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_copy_protect_key">DVD_COPY_PROTECT_KEY</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_copy_protect_key">DVD_COPY_PROTECT_KEY</a>
