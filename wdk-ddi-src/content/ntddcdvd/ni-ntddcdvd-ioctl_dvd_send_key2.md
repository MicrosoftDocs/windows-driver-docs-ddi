---
UID: NI:ntddcdvd.IOCTL_DVD_SEND_KEY2
title: IOCTL_DVD_SEND_KEY2 (ntddcdvd.h)
description: Sends the specified key to a DVD device -to complete the related step in an authentication sequence. The IOCTL_DVD_SEND_KEY2 request has write access to the device and can send a broader range of key types than IOCTL_DVD_SEND_KEY.
old-location: storage\ioctl_dvd_send_key2.htm
tech.root: storage
ms.assetid: 58b9c2a5-cd29-4c62-b5ae-39911821e3b7
ms.date: 03/29/2018
keywords: ["IOCTL_DVD_SEND_KEY2 IOCTL"]
ms.keywords: IOCTL_DVD_SEND_KEY2, IOCTL_DVD_SEND_KEY2 control, IOCTL_DVD_SEND_KEY2 control code [Storage Devices], k307_f38bdf8b-8bdc-4f28-bf53-d42f8b04a610.xml, ntddcdvd/IOCTL_DVD_SEND_KEY2, storage.ioctl_dvd_send_key2
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
 - IOCTL_DVD_SEND_KEY2
 - ntddcdvd/IOCTL_DVD_SEND_KEY2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_DVD_SEND_KEY2
---

# IOCTL_DVD_SEND_KEY2 IOCTL


## -description

Sends the specified key to a DVD device -to complete the related step in an authentication sequence. The IOCTL_DVD_SEND_KEY2 request has write access to the device and can send a broader range of key types than <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_dvd_send_key">IOCTL_DVD_SEND_KEY</a>.

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