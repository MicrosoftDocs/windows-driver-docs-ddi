---
UID: NI:ntddcdvd.IOCTL_AACS_READ_VOLUME_ID
title: IOCTL_AACS_READ_VOLUME_ID (ntddcdvd.h)
description: Reads the Advanced Access Content System (AACS)-specific volume identifier.
old-location: storage\ioctl_aacs_read_volume_id.htm
tech.root: storage
ms.assetid: 8772a83a-06e3-48f8-9d41-47332122ec8b
ms.date: 03/29/2018
ms.keywords: IOCTL_AACS_READ_VOLUME_ID, IOCTL_AACS_READ_VOLUME_ID control, IOCTL_AACS_READ_VOLUME_ID control code [Storage Devices], k307_ec201772-11c1-4825-8a71-f00f621a1b04.xml, ntddcdvd/IOCTL_AACS_READ_VOLUME_ID, storage.ioctl_aacs_read_volume_id
f1_keywords:
 - "ntddcdvd/IOCTL_AACS_READ_VOLUME_ID"
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
- IOCTL_AACS_READ_VOLUME_ID
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_AACS_READ_VOLUME_ID IOCTL


## -description


Reads the Advanced Access Content System (AACS)-specific volume identifier. 


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a value of type <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session that is associated with the volume.


### -input-buffer-length

Length of a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a>.


### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_volume_id">AACS_VOLUME_ID</a> that specifies the volume ID. 


### -output-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_volume_id">AACS_VOLUME_ID</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks



The IOCTL_AACS_READ_VOLUME_ID request corresponds to the part of the AACS authentication protocol that is responsible for transfering the volume identifier. For a complete description of this protocol, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA). 

The AGID is automatically released after the IOCTL_AACS_READ_VOLUME_ID request completes. 



