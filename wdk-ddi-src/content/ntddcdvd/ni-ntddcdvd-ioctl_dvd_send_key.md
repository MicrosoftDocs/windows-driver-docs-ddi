---
UID: NI:ntddcdvd.IOCTL_DVD_SEND_KEY
title: IOCTL_DVD_SEND_KEY (ntddcdvd.h)
description: Sends the specified key to a DVD device to complete the related step in an authentication sequence.This IOCTL has only read access to the device and cannot send keys that make alterations to the hardware configuration.
old-location: storage\ioctl_dvd_send_key.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_DVD_SEND_KEY IOCTL"]
ms.keywords: IOCTL_DVD_SEND_KEY, IOCTL_DVD_SEND_KEY control, IOCTL_DVD_SEND_KEY control code [Storage Devices], k307_9c0512f6-da79-4da0-a779-5a870ffe4b91.xml, ntddcdvd/IOCTL_DVD_SEND_KEY, storage.ioctl_dvd_send_key
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
 - IOCTL_DVD_SEND_KEY
 - ntddcdvd/IOCTL_DVD_SEND_KEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_DVD_SEND_KEY
---

# IOCTL_DVD_SEND_KEY IOCTL


## -description

Sends the specified key to a DVD device to complete the related step in an authentication sequence.

This IOCTL has only read access to the device and cannot send keys that make alterations to the hardware configuration. Therefore, this request is limited to sending key types <b>DvdChallengeKey</b>, <b>DvdBusKey2</b>, and <b>DvdInvalidateAGID</b>. 

The <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_dvd_send_key2">IOCTL_DVD_SEND_KEY2</a> request has write access to the device and is not limited to these three key types. 

For more information, see <a href="/windows-hardware/drivers/ddi/ntddcdvd/ne-ntddcdvd-dvd_key_type">DVD_KEY_TYPE</a>.

## -ioctlparameters

### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_copy_protect_key">DVD_COPY_PROTECT_KEY</a> structure that indicates the session ID, key type, and key to be sent to the device.

### -input-buffer-length

Length of a <a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_copy_protect_key">DVD_COPY_PROTECT_KEY</a>.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_copy_protect_key">DVD_COPY_PROTECT_KEY</a>
