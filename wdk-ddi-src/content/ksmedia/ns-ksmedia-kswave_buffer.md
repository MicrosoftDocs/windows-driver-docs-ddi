---
UID: NS:ksmedia.__unnamed_struct_54
title: KSWAVE_BUFFER (ksmedia.h)
description: The KSWAVE_BUFFER structure is used to describe a sample buffer.
old-location: stream\kswave_buffer.htm
tech.root: stream
ms.assetid: 1bd19fcd-90da-4e1a-ac9a-692c6fddc7ab
ms.date: 04/30/2019
keywords: ["KSWAVE_BUFFER structure"]
ms.keywords: "*PKSWAVE_BUFFER, KSWAVE_BUFFER, KSWAVE_BUFFER structure [Streaming Media Devices], PKSWAVE_BUFFER, PKSWAVE_BUFFER structure pointer [Streaming Media Devices], dvdref_8b774201-3725-497e-8545-10c5cad2ef1f.xml, ksmedia/KSWAVE_BUFFER, ksmedia/PKSWAVE_BUFFER, stream.kswave_buffer"
f1_keywords:
 - "ksmedia/KSWAVE_BUFFER"
 - "KSWAVE_BUFFER"
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
- KSWAVE_BUFFER
targetos: Windows
req.typenames: KSWAVE_BUFFER, *PKSWAVE_BUFFER
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



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-wave-buffer">KSPROPERTY_WAVE_BUFFER</a> property.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-wave-buffer">KSPROPERTY_WAVE_BUFFER</a>
 

 

