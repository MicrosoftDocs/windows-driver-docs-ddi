---
UID: NS:ks.__unnamed_struct_14
title: KSQUERYBUFFER (ks.h)
description: The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER.
old-location: stream\ksquerybuffer.htm
tech.root: stream
ms.assetid: 6827df53-f970-4ceb-961d-b4b95fa56cfe
ms.date: 04/23/2018
keywords: ["KSQUERYBUFFER structure"]
ms.keywords: "*PKSQUERYBUFFER, KSQUERYBUFFER, KSQUERYBUFFER structure [Streaming Media Devices], PKSQUERYBUFFER, PKSQUERYBUFFER structure pointer [Streaming Media Devices], ks-struct_aa45ed01-603d-4452-8862-649a73361c48.xml, ks/KSQUERYBUFFER, ks/PKSQUERYBUFFER, stream.ksquerybuffer"
f1_keywords:
 - "ks/KSQUERYBUFFER"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSQUERYBUFFER
product:
- Windows
targetos: Windows
req.typenames: KSQUERYBUFFER, *PKSQUERYBUFFER
---

# KSQUERYBUFFER structure


## -description


The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER<b>.</b>


## -struct-fields




### -field Event

Specifies the description of the original event, with the KSEVENT_TYPE_QUERYBUFFER flag set instead of the KSEVENT_TYPE_ENABLEBUFFERED flag.


### -field EventData

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> structure. This is the same pointer supplied to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksaddevent">AVStrMiniAddEvent</a> at event enable time. This pointer is used as the unique identifier in locating the event, just as it is used when disabling the event.


### -field Reserved

Not used, and set to zero.


## -remarks



If KSEVENT_TYPE_ENABLEBUFFERED was used to enable an event that also buffers data, then the data produced by the event can be queried using this method. The description of the event being queried is provided as the first parameter, and any buffer is provided as the second parameter to the query.

The buffer length needed can be queried by providing a zero length output buffer. The size of buffer is returned in the <b>BytesReturned</b> parameter, with a warning status of STATUS_BUFFER_OVERFLOW.

Alternatively, the query returns one of the following status values:

<table>
<tr>
<th>Return Value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_NOT_FOUND

</td>
<td>
event was not found

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
it was not being buffered

</td>
</tr>
<tr>
<td>
STATUS_NO_MORE_ENTRIES

</td>
<td>
no buffers were available

</td>
</tr>
<tr>
<td>
STATUS_BUFFER_TOO_SMALL

</td>
<td>
buffer size was insufficient.

</td>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
life is good.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksbuffer_item">KSBUFFER_ITEM</a>



<a href="https://docs.microsoft.com/previous-versions/ff561744(v=vs.85)">KSEVENT</a>
 

 

