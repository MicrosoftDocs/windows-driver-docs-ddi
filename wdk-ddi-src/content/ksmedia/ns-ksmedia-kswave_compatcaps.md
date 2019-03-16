---
UID: NS:ksmedia.__unnamed_struct_48
title: KSWAVE_COMPATCAPS (ksmedia.h)
description: The KSWAVE_COMPATCAPS structure is used to describe the compatible capabilities of a device.
old-location: stream\kswave_compatcaps.htm
tech.root: stream
ms.assetid: 92e6090e-6a31-45d9-ac6d-a20bf180f12e
ms.date: 04/23/2018
ms.keywords: "*PKSWAVE_COMPATCAPS, KSWAVE_COMPATCAPS, KSWAVE_COMPATCAPS structure [Streaming Media Devices], PKSWAVE_COMPATCAPS, PKSWAVE_COMPATCAPS structure pointer [Streaming Media Devices], dvdref_496e945d-fb6d-47da-8668-4cb8f1b265e6.xml, ksmedia/KSWAVE_COMPATCAPS, ksmedia/PKSWAVE_COMPATCAPS, stream.kswave_compatcaps"
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
- KSWAVE_COMPATCAPS
product:
- Windows
targetos: Windows
req.typenames: KSWAVE_COMPATCAPS, *PKSWAVE_COMPATCAPS
---

# KSWAVE_COMPATCAPS structure


## -description


The KSWAVE_COMPATCAPS structure is used to describe the compatible capabilities of a device.


## -struct-fields




### -field ulDeviceType

Specifies the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSWAVE_COMPATCAPS_INPUT

</td>
<td>
Indicates that the device accepts input.

</td>
</tr>
<tr>
<td>
KSWAVE_COMPATCAPS_OUTPUT

</td>
<td>
Indicates that the device produces output.

</td>
</tr>
</table>
 


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566516">KSPROPERTY_WAVE_COMPATIBLE_CAPABILITIES</a> property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566516">KSPROPERTY_WAVE_COMPATIBLE_CAPABILITIES</a>
 

 

