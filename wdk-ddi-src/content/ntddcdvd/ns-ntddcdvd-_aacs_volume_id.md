---
UID: NS:ntddcdvd._AACS_VOLUME_ID
title: _AACS_VOLUME_ID (ntddcdvd.h)
description: The AACS_VOLUME_ID structure contains an Advanced Access Content System (AACS) volume ID and the corresponding message authentication code (MAC).
old-location: storage\aacs_volume_id.htm
tech.root: storage
ms.assetid: 3ad7a253-cc55-4613-8086-b8d08d9bd54f
ms.date: 03/29/2018
keywords: ["AACS_VOLUME_ID structure"]
ms.keywords: "*PAACS_VOLUME_ID, AACS_VOLUME_ID, AACS_VOLUME_ID structure [Storage Devices], PAACS_VOLUME_ID, PAACS_VOLUME_ID structure pointer [Storage Devices], _AACS_VOLUME_ID, ntddcdvd/AACS_VOLUME_ID, ntddcdvd/PAACS_VOLUME_ID, storage.aacs_volume_id, structs-DVD_f65fe36a-a9a4-4540-a349-2ac9827b5a91.xml"
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
req.typenames: AACS_VOLUME_ID, *PAACS_VOLUME_ID
f1_keywords:
 - _AACS_VOLUME_ID
 - ntddcdvd/_AACS_VOLUME_ID
 - PAACS_VOLUME_ID
 - ntddcdvd/PAACS_VOLUME_ID
 - AACS_VOLUME_ID
 - ntddcdvd/AACS_VOLUME_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdvd.h
api_name:
 - AACS_VOLUME_ID
---

# _AACS_VOLUME_ID structure


## -description

The AACS_VOLUME_ID structure contains an Advanced Access Content System (AACS) volume ID and the corresponding message authentication code (MAC).

## -struct-fields

### -field VolumeID

The volume identifier.

### -field MAC

The message authentication code (MAC) that the client uses to verify that the volume identifier is for the current AACS authentication sequence.

## -remarks

Clients retrieve an AACS volume ID with an <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_read_volume_id">IOCTL_AACS_READ_VOLUME_ID</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_read_volume_id">IOCTL_AACS_READ_VOLUME_ID</a>