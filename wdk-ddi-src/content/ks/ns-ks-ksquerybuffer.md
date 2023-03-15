---
UID: NS:ks.KSQUERYBUFFER
title: KSQUERYBUFFER (ks.h)
description: The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KSQUERYBUFFER structure"]
ms.keywords: "*PKSQUERYBUFFER, KSQUERYBUFFER, KSQUERYBUFFER structure [Streaming Media Devices], PKSQUERYBUFFER, PKSQUERYBUFFER structure pointer [Streaming Media Devices], ks-struct_aa45ed01-603d-4452-8862-649a73361c48.xml, ks/KSQUERYBUFFER, ks/PKSQUERYBUFFER, stream.ksquerybuffer"
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: KSQUERYBUFFER, *PKSQUERYBUFFER
f1_keywords:
 - PKSQUERYBUFFER
 - ks/PKSQUERYBUFFER
 - KSQUERYBUFFER
 - ks/KSQUERYBUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSQUERYBUFFER
 - KSQUERYBUFFER
---

## -description

The **KSQUERYBUFFER** structure is used when querying for outstanding buffers available on an event with **KSEVENT_TYPE_QUERYBUFFER**.

## -struct-fields

### -field Event

Specifies the description of the original event, with the **KSEVENT_TYPE_QUERYBUFFER** flag set instead of the **KSEVENT_TYPE_ENABLEBUFFERED** flag.

### -field EventData

A pointer to a [**KSEVENTDATA**](./ns-ks-kseventdata.md) structure. This is the same pointer supplied to [AVStrMiniAddEvent](./nc-ks-pfnksaddevent.md) at event enable time. This pointer is used as the unique identifier in locating the event, just as it is used when disabling the event.

### -field Reserved

Not used, and set to zero.

## -remarks

If **KSEVENT_TYPE_ENABLEBUFFERED** was used to enable an event that also buffers data, then the data produced by the event can be queried using this method. The description of the event being queried is provided as the first parameter, and any buffer is provided as the second parameter to the query.

The buffer length needed can be queried by providing a zero length output buffer. The size of buffer is returned in the **BytesReturned** parameter, with a warning status of **STATUS_BUFFER_OVERFLOW**.

Alternatively, the query returns one of the following status values:

| Return Value | Description |
|---|---|
| STATUS_NOT_FOUND | event was not found |
| STATUS_INVALID_PARAMETER | it was not being buffered |
| STATUS_NO_MORE_ENTRIES | no buffers were available |
| STATUS_BUFFER_TOO_SMALL | buffer size was insufficient. |
| STATUS_SUCCESS | life is good. |

## -see-also

[**KSBUFFER_ITEM**](./ns-ks-ksbuffer_item.md)

[**KSEVENT**](/windows-hardware/drivers/stream/ksevent-structure)