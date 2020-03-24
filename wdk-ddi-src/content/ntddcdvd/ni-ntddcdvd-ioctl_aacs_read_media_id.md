---
UID: NI:ntddcdvd.IOCTL_AACS_READ_MEDIA_ID
title: IOCTL_AACS_READ_MEDIA_ID (ntddcdvd.h)
description: Reads the Advanced Access Content System (AACS)-specific media identifier data.
old-location: storage\ioctl_aacs_read_media_id.htm
tech.root: storage
ms.assetid: e56f6af5-0391-4044-b6b3-efb27b511db6
ms.date: 03/29/2018
keywords: ["IOCTL_AACS_READ_MEDIA_ID IOCTL"]
ms.keywords: IOCTL_AACS_READ_MEDIA_ID, IOCTL_AACS_READ_MEDIA_ID control, IOCTL_AACS_READ_MEDIA_ID control code [Storage Devices], k307_1f0ffe88-e59a-44e5-bec0-247d38478be8.xml, ntddcdvd/IOCTL_AACS_READ_MEDIA_ID, storage.ioctl_aacs_read_media_id
f1_keywords:
 - "ntddcdvd/IOCTL_AACS_READ_MEDIA_ID"
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
- IOCTL_AACS_READ_MEDIA_ID
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_AACS_READ_MEDIA_ID IOCTL


## -description


Reads the Advanced Access Content System (AACS)-specific media identifier data.  


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a value of type <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID).  


### -input-buffer-length

Length of a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a>.


### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_media_id">AACS_MEDIA_ID</a> that specifies the media ID.


### -output-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_media_id">AACS_MEDIA_ID</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks



The IOCTL_AACS_READ_MEDIA_ID request corresponds to the part of the AACS authentication protocol that is responsible for transferring the media identifier. For a complete description of this protocol, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

The AGID is automatically released after the IOCTL_AACS_READ_MEDIA_ID request completes.



