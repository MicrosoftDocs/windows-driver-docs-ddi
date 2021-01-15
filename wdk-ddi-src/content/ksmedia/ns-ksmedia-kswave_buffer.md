---
UID: NS:ksmedia.__unnamed_struct_54
title: KSWAVE_BUFFER (ksmedia.h)
description: The KSWAVE_BUFFER structure is used to describe a sample buffer.
old-location: stream\kswave_buffer.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSWAVE_BUFFER structure"]
ms.keywords: "*PKSWAVE_BUFFER, KSWAVE_BUFFER, KSWAVE_BUFFER structure [Streaming Media Devices], PKSWAVE_BUFFER, PKSWAVE_BUFFER structure pointer [Streaming Media Devices], dvdref_8b774201-3725-497e-8545-10c5cad2ef1f.xml, ksmedia/KSWAVE_BUFFER, ksmedia/PKSWAVE_BUFFER, stream.kswave_buffer"
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
targetos: Windows
req.typenames: KSWAVE_BUFFER, *PKSWAVE_BUFFER
f1_keywords:
 - PKSWAVE_BUFFER
 - ksmedia/PKSWAVE_BUFFER
 - KSWAVE_BUFFER
 - ksmedia/KSWAVE_BUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSWAVE_BUFFER
 - KSWAVE_BUFFER
---

# KSWAVE_BUFFER structure


## -description

The KSWAVE_BUFFER structure is used to describe a sample buffer.

## -struct-fields

### -field Attributes

Specifies the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSWAVE_BUFFER_ATTRIBUTEF_LOOPING

</td>
<td>
Indicates that the buffer loops.

</td>
</tr>
<tr>
<td>
KSWAVE_BUFFER_ATTRIBUTEF_STATIC

</td>
<td>
Indicates that the buffer is static.

</td>
</tr>
</table>

### -field BufferSize

Specifies the size of the buffer, in bytes.

### -field BufferAddress

Specifies the starting address of the buffer.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/stream/ksproperty-wave-buffer">KSPROPERTY_WAVE_BUFFER</a> property.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-wave-buffer">KSPROPERTY_WAVE_BUFFER</a>

