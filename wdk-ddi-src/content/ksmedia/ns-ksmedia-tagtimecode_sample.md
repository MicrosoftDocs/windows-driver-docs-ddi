---
UID: NS:ksmedia.tagTIMECODE_SAMPLE
title: tagTIMECODE_SAMPLE (ksmedia.h)
description: The TIMECODE_SAMPLE structure describes a complete timecode.
old-location: stream\timecode_sample.htm
tech.root: stream
ms.assetid: 01654107-29a1-4f34-bb9a-a17fe36a84fe
ms.date: 04/23/2018
ms.keywords: "*PTIMECODE_SAMPLE, TIMECODE_SAMPLE, TIMECODE_SAMPLE structure [Streaming Media Devices], ksmedia/TIMECODE_SAMPLE, stream.timecode_sample, tagTIMECODE_SAMPLE, vidcapstruct_518cf1af-a1e2-43a6-b97f-115c4fe8cb6d.xml"
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- ksmedia.h
api_name:
- TIMECODE_SAMPLE
product:
- Windows
targetos: Windows
req.typenames: TIMECODE_SAMPLE
---

# tagTIMECODE_SAMPLE structure


## -description


The TIMECODE_SAMPLE structure describes a complete timecode.


## -struct-fields




### -field qwTick

Specifies a reference time, in 100-nanosecond units.


### -field timecode

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-_timecode">TIMECODE</a> structure.


### -field dwUser

Specifies packed SMPTE user-bits.


### -field dwFlags

Specifies any optional timecode flag masks.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
AM_TIMECODE_FLAG_FCM

</td>
<td>
Frame-code mode; 0 = nondrop; 1 = drop.

</td>
</tr>
<tr>
<td>
AM_TIMECODE_FLAG_CF

</td>
<td>
Color-frame flag.

</td>
</tr>
<tr>
<td>
AM_TIMECODE_FLAG_FIELD

</td>
<td>
Field flag.

</td>
</tr>
<tr>
<td>
AM_TIMECODE_FLAG_DF

</td>
<td>
Drop-frame flag (from flags in actual timecode on external media).

</td>
</tr>
<tr>
<td>
AM_TIMECODE_COLORFRAME

</td>
<td>
Specifies frame, in color sequence.

</td>
</tr>
<tr>
<td>
AM_TIMECODE_COLORSEQUENCE

</td>
<td>
Duration, in frames, of complete sequence.

</td>
</tr>
<tr>
<td>
AM_TIMECODE_FILMSEQUENCE_TYPE

</td>
<td>
One of the FILM_SEQUENCE_<i>XXX</i> tokens.

</td>
</tr>
<tr>
<td>
ED_DEVCAP_TIMECODE_READ

</td>
<td>
Read SMPTE timecode; applies to DV camcorders.

</td>
</tr>
<tr>
<td>
ED_DEVCAP_ATN_READ

</td>
<td>
Read the absolute track number (ATN); applies to DV camcorders.

</td>
</tr>
<tr>
<td>
ED_DEVCAP_RTC_READ

</td>
<td>
Read the relative time counter (RTC); applies to MPEG camcorders.

</td>
</tr>
</table>
 


## -remarks



Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the DirectX SDK.

The upper 16 bits in <b>dwFlags</b> are reserved for future use and must be set to zero.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-_timecode">TIMECODE</a>
 

 

