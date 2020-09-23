---
UID: NS:ksmedia.__unnamed_struct_90
title: KSPROPERTY_VIDEOPROCAMP_S (ksmedia.h)
description: The KSPROPERTY_VIDEOPROCAMP_S structure describes filter-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set.
old-location: stream\ksproperty_videoprocamp_s.htm
tech.root: stream
ms.assetid: e8b9c381-2159-4cb2-92e2-11c1d3698f2d
ms.date: 04/30/2019
keywords: ["KSPROPERTY_VIDEOPROCAMP_S structure"]
ms.keywords: "*PKSPROPERTY_VIDEOPROCAMP_S, KSPROPERTY_VIDEOPROCAMP_S, KSPROPERTY_VIDEOPROCAMP_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOPROCAMP_S, PKSPROPERTY_VIDEOPROCAMP_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOPROCAMP_S, ksmedia/PKSPROPERTY_VIDEOPROCAMP_S, stream.ksproperty_videoprocamp_s, vidcapstruct_4ec1fd8e-6ea5-4560-a528-e6cd2023ec87.xml"
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
req.typenames: KSPROPERTY_VIDEOPROCAMP_S, *PKSPROPERTY_VIDEOPROCAMP_S
f1_keywords:
 - PKSPROPERTY_VIDEOPROCAMP_S
 - ksmedia/PKSPROPERTY_VIDEOPROCAMP_S
 - KSPROPERTY_VIDEOPROCAMP_S
 - ksmedia/KSPROPERTY_VIDEOPROCAMP_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_VIDEOPROCAMP_S
---

# KSPROPERTY_VIDEOPROCAMP_S structure


## -description

The KSPROPERTY_VIDEOPROCAMP_S structure describes filter-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set.

## -struct-fields

### -field Property

Specifies an initialized <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in <b>Property</b> to this value. For Get requests, the minidriver should return the value of the property specified in <b>Property</b>.

### -field Flags

Specifies the flags of a request. For Set requests, this value indicates the desired setting. For Get requests, this value contains the current setting. This member can be set to one of the values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL

</td>
<td>
Indicates that the property is to be adjusted manually.

</td>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO

</td>
<td>
Indicates that the property is to be adjusted automatically.

</td>
</tr>
</table>

### -field Capabilities

Specifies the capabilities of a property. This member has meaning only for Get requests. The minidriver should return the capabilities of the VideoProcAmp with respect to the property specified in <b>Property</b>. This member should be set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL

</td>
<td>
The device supports manual setting of the specified property.

</td>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO

</td>
<td>
The device supports automatic setting of the specified property.

</td>
</tr>
</table>

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-backlight-compensation">KSPROPERTY_VIDEOPROCAMP_BACKLIGHT_COMPENSATION</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-brightness">KSPROPERTY_VIDEOPROCAMP_BRIGHTNESS</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-colorenable">KSPROPERTY_VIDEOPROCAMP_COLORENABLE</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-contrast">KSPROPERTY_VIDEOPROCAMP_CONTRAST</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-gamma">KSPROPERTY_VIDEOPROCAMP_GAMMA</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-hue">KSPROPERTY_VIDEOPROCAMP_HUE</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-saturation">KSPROPERTY_VIDEOPROCAMP_SATURATION</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-sharpness">KSPROPERTY_VIDEOPROCAMP_SHARPNESS</a>



<a href="/windows-hardware/drivers/stream/ksproperty-videoprocamp-whitebalance">KSPROPERTY_VIDEOPROCAMP_WHITEBALANCE</a>



<a href="/windows-hardware/drivers/stream/propsetid-vidcap-videoprocamp">PROPSETID_VIDCAP_VIDEOPROCAMP</a>