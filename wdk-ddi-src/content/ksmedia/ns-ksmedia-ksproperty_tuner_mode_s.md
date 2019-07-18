---
UID: NS:ksmedia.__unnamed_struct_99
title: KSPROPERTY_TUNER_MODE_S (ksmedia.h)
description: The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device.
old-location: stream\ksproperty_tuner_mode_s.htm
tech.root: stream
ms.assetid: a3e443e5-1766-4292-a25a-ad673734bac1
ms.date: 04/30/2019
ms.keywords: "*PKSPROPERTY_TUNER_MODE_S, KSPROPERTY_TUNER_MODE_S, KSPROPERTY_TUNER_MODE_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_MODE_S, PKSPROPERTY_TUNER_MODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_MODE_S, ksmedia/PKSPROPERTY_TUNER_MODE_S, stream.ksproperty_tuner_mode_s, vidcapstruct_fe1fe8d4-8abd-4db3-8438-ef7dddadfa5c.xml"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSPROPERTY_TUNER_MODE_S"
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
- KSPROPERTY_TUNER_MODE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_MODE_S, *PKSPROPERTY_TUNER_MODE_S
---

# KSPROPERTY_TUNER_MODE_S structure


## -description


The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Mode

Specifies the current tuner mode. If the request is a Get request, the minidriver should return the current tuner mode. If the request is a Set request, the minidriver should switch the current tuner mode to the specified value. This member can be one of the following tuner modes from the KSPROPERTY_TUNER_MODES enumeration that is defined in <i>K</i><i>smedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_TV

</td>
<td>
Indicates that the tuner is currently tuning (get) or should switch to tuning broadcast or cable television channels (set).

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_FM_RADIO

</td>
<td>
Indicates that the tuner is currently tuning (get) or should switch to tuning (set) FM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_AM_RADIO

</td>
<td>
Indicates that the tuner is currently tuning (get) or should switch to tuning (set) AM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_DSS

</td>
<td>
Indicates that the tuner is currently tuning (get) or should switch to tuning (set) tuning DSS channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_ATSC

</td>
<td>
Indicates that the tuner is capable of tuning (get) or should switch to tuning (set) Advanced Television Systems Committee broadcasts (Digital TV for the United States). This setting can also be used by DVB-T and DVB-C systems.

</td>
</tr>
</table>
 


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-mode">KSPROPERTY_TUNER_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-tuner">PROPSETID_TUNER</a>
 

 

