---
UID: NS:ksmedia.KSPROPERTY_VIDEOPROCAMP_S
title: KSPROPERTY_VIDEOPROCAMP_S (ksmedia.h)
description: The KSPROPERTY_VIDEOPROCAMP_S structure describes filter-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set.
tech.root: stream
ms.date: 04/17/2023
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
 - PKSPROPERTY_VIDEOPROCAMP_S
 - KSPROPERTY_VIDEOPROCAMP_S
---

# KSPROPERTY_VIDEOPROCAMP_S structure

## -description

The **KSPROPERTY_VIDEOPROCAMP_S** structure describes filter-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in **Property** to this value. For Get requests, the minidriver should return the value of the property specified in **Property**.

### -field Flags

Specifies the flags of a request. For Set requests, this value indicates the desired setting. For Get requests, this value contains the current setting. This member can be set to one of the values that are defined in *ksmedia.h*:

| Flag | Meaning |
|--|--|
| KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL | Indicates that the property is to be adjusted manually. |
| KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO | Indicates that the property is to be adjusted automatically. |

### -field Capabilities

Specifies the capabilities of a property. This member has meaning only for Get requests. The minidriver should return the capabilities of the VideoProcAmp with respect to the property specified in **Property**. This member should be set to one of the following values:

| Value | Meaning |
|--|--|
| KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL | The device supports manual setting of the specified property. |
| KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO | The device supports automatic setting of the specified property. |

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_VIDEOPROCAMP_BACKLIGHT_COMPENSATION](/windows-hardware/drivers/stream/ksproperty-videoprocamp-backlight-compensation)

[KSPROPERTY_VIDEOPROCAMP_BRIGHTNESS](/windows-hardware/drivers/stream/ksproperty-videoprocamp-brightness)

[KSPROPERTY_VIDEOPROCAMP_COLORENABLE](/windows-hardware/drivers/stream/ksproperty-videoprocamp-colorenable)

[KSPROPERTY_VIDEOPROCAMP_CONTRAST](/windows-hardware/drivers/stream/ksproperty-videoprocamp-contrast)

[KSPROPERTY_VIDEOPROCAMP_GAMMA](/windows-hardware/drivers/stream/ksproperty-videoprocamp-gamma)

[KSPROPERTY_VIDEOPROCAMP_HUE](/windows-hardware/drivers/stream/ksproperty-videoprocamp-hue)

[KSPROPERTY_VIDEOPROCAMP_SATURATION](/windows-hardware/drivers/stream/ksproperty-videoprocamp-saturation)

[KSPROPERTY_VIDEOPROCAMP_SHARPNESS](/windows-hardware/drivers/stream/ksproperty-videoprocamp-sharpness)

[KSPROPERTY_VIDEOPROCAMP_WHITEBALANCE](/windows-hardware/drivers/stream/ksproperty-videoprocamp-whitebalance)

[PROPSETID_VIDCAP_VIDEOPROCAMP](/windows-hardware/drivers/stream/propsetid-vidcap-videoprocamp)
