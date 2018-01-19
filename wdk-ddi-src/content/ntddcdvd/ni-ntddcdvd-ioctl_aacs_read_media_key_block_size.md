---
UID: NI:ntddcdvd.IOCTL_AACS_READ_MEDIA_KEY_BLOCK_SIZE
title: IOCTL_AACS_READ_MEDIA_KEY_BLOCK_SIZE
author: windows-driver-content
description: Queries the logical unit for the size of the buffer that is required to hold the Advanced Access Control System (AACS) Media Key Block (MKB).
old-location: storage\ioctl_aacs_read_media_key_block_size.htm
old-project: storage
ms.assetid: 2b8e5461-c935-46d8-afe3-c82a7566a4c7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_AACS_READ_MEDIA_KEY_BLOCK_SIZE
req.alt-loc: Ntddcdvd.h
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
req.typenames: *PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT
---

# IOCTL_AACS_READ_MEDIA_KEY_BLOCK_SIZE IOCTL



## -description
Queries the logical unit for the size of the buffer that is required to hold the Advanced Access Control System (AACS) Media Key Block (MKB). 



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the AACS_LAYER_NUMBER number of the layer. The AACS_LAYER_NUMBER is an unsigned long integer value in the range 0 to 255 inclusive that specifies the layer of the media to which a command applies.

<code>typedef ULONG AACS_LAYER_NUMBER, *PAACS_LAYER_NUMBER;
</code>


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(AACS_LAYER_NUMBER).


### -output-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a ULONG that holds the size in bytes of the full AACS MKB for this media.


### -output-buffer-length
Use this value to determine the size of the buffer to allocate for <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_media_key_block.md">IOCTL_AACS_READ_MEDIA_KEY_BLOCK</a>. The size is always a multiple of 32,768 (0x8000).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS if the operation succeeds. The following failure codes are common with this operation:



Failure of one of the copy protection mechanisms.

The authentication process has failed.

No AACS protection exists for this media.

The AGID for AACS has not been established.


## -remarks
The IOCTL_AACS_READ_MEDIA_KEY_BLOCK_SIZE request will not work if the media in the logical unit is not AACS protected.

The IOCTL_AACS_READ_MEDIA_KEY_BLOCK_SIZE request corresponds to one of the steps of the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth). For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).</p>