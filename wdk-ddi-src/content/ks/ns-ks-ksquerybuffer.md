---
UID: NS:ks.KSQUERYBUFFER
title: KSQUERYBUFFER
author: windows-driver-content
description: The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER.
old-location: stream\ksquerybuffer.htm
old-project: stream
ms.assetid: 6827df53-f970-4ceb-961d-b4b95fa56cfe
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSQUERYBUFFER, *PKSQUERYBUFFER, KSQUERYBUFFER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSQUERYBUFFER
req.alt-loc: ks.h
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
req.typenames: *PKSQUERYBUFFER, KSQUERYBUFFER
---

# KSQUERYBUFFER structure



## -description
The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER<b>.</b>



## -syntax

````
typedef struct {
  KSEVENT      Event;
  PKSEVENTDATA EventData;
  PVOID        Reserved;
} KSQUERYBUFFER, *PKSQUERYBUFFER;
````


## -struct-fields

### -field Event

Specifies the description of the original event, with the KSEVENT_TYPE_QUERYBUFFER flag set instead of the KSEVENT_TYPE_ENABLEBUFFERED flag.


### -field EventData

A pointer to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure. This is the same pointer supplied to <a href="..\ks\nc-ks-pfnksaddevent.md">AVStrMiniAddEvent</a> at event enable time. This pointer is used as the unique identifier in locating the event, just as it is used when disabling the event.


### -field Reserved

Not used, and set to zero.


## -remarks
If KSEVENT_TYPE_ENABLEBUFFERED was used to enable an event that also buffers data, then the data produced by the event can be queried using this method. The description of the event being queried is provided as the first parameter, and any buffer is provided as the second parameter to the query.

The buffer length needed can be queried by providing a zero length output buffer. The size of buffer is returned in the <b>BytesReturned</b> parameter, with a warning status of STATUS_BUFFER_OVERFLOW.

Alternatively, the query returns one of the following status values:

STATUS_NOT_FOUND

event was not found

STATUS_INVALID_PARAMETER

it was not being buffered

STATUS_NO_MORE_ENTRIES

no buffers were available

STATUS_BUFFER_TOO_SMALL

buffer size was insufficient.

STATUS_SUCCESS

life is good.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksbuffer_item.md">KSBUFFER_ITEM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSQUERYBUFFER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

