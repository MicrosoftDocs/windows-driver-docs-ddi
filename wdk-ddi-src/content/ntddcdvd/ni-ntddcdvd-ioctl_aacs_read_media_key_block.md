---
UID: NI:ntddcdvd.IOCTL_AACS_READ_MEDIA_KEY_BLOCK
title: IOCTL_AACS_READ_MEDIA_KEY_BLOCK (ntddcdvd.h)
description: Queries the logical unit for the Media Key Block (MKB).
old-location: storage\ioctl_aacs_read_media_key_block.htm
tech.root: storage
ms.assetid: 08852f41-1836-4c55-bf6f-0246caa2c8bd
ms.date: 03/29/2018
keywords: ["IOCTL_AACS_READ_MEDIA_KEY_BLOCK IOCTL"]
ms.keywords: IOCTL_AACS_READ_MEDIA_KEY_BLOCK, IOCTL_AACS_READ_MEDIA_KEY_BLOCK control, IOCTL_AACS_READ_MEDIA_KEY_BLOCK control code [Storage Devices], k307_0e90884e-4c78-4fd5-b30c-eed14d73ba5e.xml, ntddcdvd/IOCTL_AACS_READ_MEDIA_KEY_BLOCK, storage.ioctl_aacs_read_media_key_block
f1_keywords:
 - "ntddcdvd/IOCTL_AACS_READ_MEDIA_KEY_BLOCK"
 - "IOCTL_AACS_READ_MEDIA_KEY_BLOCK"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddcdvd.h
api_name:
- IOCTL_AACS_READ_MEDIA_KEY_BLOCK
targetos: Windows
req.typenames: 
---

# IOCTL_AACS_READ_MEDIA_KEY_BLOCK IOCTL


## -description


Queries the logical unit for the Media Key Block (MKB).


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the AACS_LAYER_NUMBER number of the layer. The AACS_LAYER_NUMBER is an unsigned long integer value in the range 0 to 255 inclusive that specifies the layer of the media to which a command applies.

<code>typedef ULONG AACS_LAYER_NUMBER, *PAACS_LAYER_NUMBER;
</code>


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(AACS_LAYER_NUMBER). 


### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains an opaque, variable-length MKB. The size of the MKB is always a multiple of 32,768 (0x8000). 


### -output-buffer-length

Length of a variable-length MKB.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS if the operation succeeds. If <b>Irp->AssociatedIrp.SystemBuffer </b>is <b>NULL</b> or the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> is not sufficient to contain the full MKB, the operation fails and returns a status of STATUS_BUFFER_TOO_SMALL, and the required buffer size is returned in <b>IoStatus.Information</b>.


## -remarks



The storage stack uses a READ DISC STRUCTURE command (format 0x17) with Advanced Access Control System (AACS) extensions to retrieve the MKB. IOCTL_AACS_READ_MEDIA_KEY_BLOCK request will not work if the media in the logical unit is not AACS protected. 

Unlike the MKB that is used with Content-Scrambling System (CSS) encryption, AACS MKBs are self-protected with digital signatures. The MKB structure is fully documented in the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

The IOCTL_AACS_READ_MEDIA_KEY_BLOCK request corresponds to one of the steps of the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth). For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification.



