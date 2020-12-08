---
UID: NS:ntddcdvd._AACS_MEDIA_ID
title: _AACS_MEDIA_ID (ntddcdvd.h)
description: The AACS_MEDIA_ID structure contains an Advanced Access Content System (AACS) media identifier and corresponding message authentication code (MAC).
old-location: storage\aacs_media_id.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AACS_MEDIA_ID structure"]
ms.keywords: "*PAACS_MEDIA_ID, AACS_MEDIA_ID, AACS_MEDIA_ID structure [Storage Devices], PAACS_MEDIA_ID, PAACS_MEDIA_ID structure pointer [Storage Devices], _AACS_MEDIA_ID, ntddcdvd/AACS_MEDIA_ID, ntddcdvd/PAACS_MEDIA_ID, storage.aacs_media_id, structs-DVD_413a14c6-75e0-444f-b325-8dfeb9c0c074.xml"
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
req.typenames: AACS_MEDIA_ID, *PAACS_MEDIA_ID
f1_keywords:
 - _AACS_MEDIA_ID
 - ntddcdvd/_AACS_MEDIA_ID
 - PAACS_MEDIA_ID
 - ntddcdvd/PAACS_MEDIA_ID
 - AACS_MEDIA_ID
 - ntddcdvd/AACS_MEDIA_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdvd.h
api_name:
 - AACS_MEDIA_ID
---

# _AACS_MEDIA_ID structure


## -description

The AACS_MEDIA_ID structure contains an Advanced Access Content System (AACS) media identifier and corresponding message authentication code (MAC).

## -struct-fields

### -field MediaID

The media identifier.

### -field MAC

The message authentication code (MAC) that the client uses to verify that the MediaID is for the current AACS authentication sequence.

## -remarks

Clients retrieve the AACS certificate with an <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_read_media_id">IOCTL_AACS_READ_MEDIA_ID</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_read_media_id">IOCTL_AACS_READ_MEDIA_ID</a>
