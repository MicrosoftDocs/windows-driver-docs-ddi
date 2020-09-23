---
UID: NS:ksmedia.__unnamed_struct_98
title: KSPROPERTY_TUNER_MODE_CAPS_S (ksmedia.h)
description: The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices.
old-location: stream\ksproperty_tuner_mode_caps_s.htm
tech.root: stream
ms.assetid: e2376cde-7e13-475d-a118-0cf48ba8a742
ms.date: 04/30/2019
keywords: ["KSPROPERTY_TUNER_MODE_CAPS_S structure"]
ms.keywords: "*PKSPROPERTY_TUNER_MODE_CAPS_S, KSPROPERTY_TUNER_MODE_CAPS_S, KSPROPERTY_TUNER_MODE_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_MODE_CAPS_S, PKSPROPERTY_TUNER_MODE_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_MODE_CAPS_S, ksmedia/PKSPROPERTY_TUNER_MODE_CAPS_S, stream.ksproperty_tuner_mode_caps_s, vidcapstruct_d80882b8-2962-48c3-b2e9-393deec31ccc.xml"
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
req.typenames: KSPROPERTY_TUNER_MODE_CAPS_S, *PKSPROPERTY_TUNER_MODE_CAPS_S
f1_keywords:
 - PKSPROPERTY_TUNER_MODE_CAPS_S
 - ksmedia/PKSPROPERTY_TUNER_MODE_CAPS_S
 - KSPROPERTY_TUNER_MODE_CAPS_S
 - ksmedia/KSPROPERTY_TUNER_MODE_CAPS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_TUNER_MODE_CAPS_S
---

# KSPROPERTY_TUNER_MODE_CAPS_S structure


## -description

The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices.

## -struct-fields

### -field Property

Specifies an initialized <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field Mode

Specifies the tuner mode that the caller is requesting capability information about. It can be one of the following tuner modes from the KSPROPERTY_TUNER_MODES enumeration that is defined in <i>ksmedia.h</i>:

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
Indicates that the tuner is capable of tuning Advanced Television Systems Committee broadcasts (Digital TV for the United States) or other digital television standard.

</td>
</tr>
</table>

### -field StandardsSupported

Describes the analog video standards supported. If <b>Mode</b> is set to KSPROPERTY_TUNER_MODE_TV, this member may be set to one or more (logically ORed) values from the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a> enumeration.

### -field MinFrequency

Specifies the lowest frequency supported by the tuner. This value is in hertz (Hz).

### -field MaxFrequency

Specifies the highest frequency supported by the tuner. This value is in hertz (Hz).

### -field TuningGranularity

Specifies the smallest possible step size between two settings of the tuning frequency. This value is in hertz (Hz).

### -field NumberOfInputs

Specifies the number of inputs on the tuner.

### -field SettlingTime

Specifies the time, in milliseconds, for a new frequency setting to become stable.

### -field Strategy

Specifies the tuning method. This member must be set to only one of the values from the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_tuner_strategy">KS_TUNER_STRATEGY</a> enumeration.

## -remarks

The minidriver fills in the mode capabilities for the requested tuner mode.

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-tuner-mode-caps">KSPROPERTY_TUNER_MODE_CAPS</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_tuner_strategy">KS_TUNER_STRATEGY</a>



<a href="/windows-hardware/drivers/stream/propsetid-tuner">PROPSETID_TUNER</a>