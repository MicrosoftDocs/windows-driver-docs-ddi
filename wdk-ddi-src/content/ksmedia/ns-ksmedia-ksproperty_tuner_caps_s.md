---
UID: NS:ksmedia.__unnamed_struct_96
title: KSPROPERTY_TUNER_CAPS_S (ksmedia.h)
description: The KSPROPERTY_TUNER_CAPS_S structure describes the hardware capabilities of TV and radio tuning devices.
old-location: stream\ksproperty_tuner_caps_s.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSPROPERTY_TUNER_CAPS_S structure"]
ms.keywords: "*PKSPROPERTY_TUNER_CAPS_S, KSPROPERTY_TUNER_CAPS_S, KSPROPERTY_TUNER_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_CAPS_S, PKSPROPERTY_TUNER_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_CAPS_S, ksmedia/PKSPROPERTY_TUNER_CAPS_S, stream.ksproperty_tuner_caps_s, vidcapstruct_28e3b0b2-5b4e-404a-8ade-d5d9c1870ae5.xml"
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
req.typenames: KSPROPERTY_TUNER_CAPS_S, *PKSPROPERTY_TUNER_CAPS_S
f1_keywords:
 - PKSPROPERTY_TUNER_CAPS_S
 - ksmedia/PKSPROPERTY_TUNER_CAPS_S
 - KSPROPERTY_TUNER_CAPS_S
 - ksmedia/KSPROPERTY_TUNER_CAPS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_TUNER_CAPS_S
 - KSPROPERTY_TUNER_CAPS_S
---

# KSPROPERTY_TUNER_CAPS_S structure


## -description

The KSPROPERTY_TUNER_CAPS_S structure describes the hardware capabilities of TV and radio tuning devices.

## -struct-fields

### -field Property

Specifies an initialized <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field ModesSupported

Specifies a bitwise OR of the supported tuner modes. This member may be set to one or more of the following values from the KSPROPERTY_TUNER_MODES enumeration that is defined in <i>ksmedia.h</i>:

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
Indicates that the tuner is capable of tuning analog broadcast or cable television channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_FM_RADIO

</td>
<td>
Indicates that the tuner is capable of tuning FM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_AM_RADIO

</td>
<td>
Indicates that the tuner is capable of tuning AM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_DSS

</td>
<td>
Indicates that the tuner is capable of tuning DSS channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_ATSC

</td>
<td>
Indicates that the tuner is capable of tuning digital television channels. This setting can be used for ATSC, DVB-C, or DVB-T television reception.

</td>
</tr>
</table>

### -field VideoMedium

Specifies a unique GUID representing the hardware connection of the analog video signal. This value enforces connections between filters. Possible values are <b>NULL</b>, indicating that no pin is created; GUID_NULL, indicating that Medium is not used to enforce connections; or a GUID. If a GUID value is used, only crossbar pins with a matching Medium GUID are allowed to connect.

### -field TVAudioMedium

Specifies a unique GUID representing the hardware connection of the TV audio signal. This value enforces connections between filters. Possible values are <b>NULL</b>, indicating that no pin is created; GUID_NULL, indicating that Medium is not used to enforce connections; or a GUID. If a GUID value is used, only crossbar pins with a matching Medium GUID are allowed to connect.

### -field RadioAudioMedium

Specifies a unique GUID representing the hardware connection of the analog radio audio signal. This value enforces connections between filters. Possible values are <b>NULL</b>, indicating that no pin is created; GUID_NULL, indicating that Medium is not used to enforce connections; or a GUID. If a GUID value is used, only crossbar pins with a matching Medium GUID are allowed to connect.

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-tuner-caps">KSPROPERTY_TUNER_CAPS</a>



<a href="/windows-hardware/drivers/stream/ksproperty-tuner-if-medium">KSPROPERTY_TUNER_IF_MEDIUM</a>



<a href="/windows-hardware/drivers/stream/propsetid-tuner">PROPSETID_TUNER</a>

