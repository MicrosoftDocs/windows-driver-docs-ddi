---
UID: NS:ksmedia.KSPROPERTY_TUNER_MODE_CAPS_S
title: KSPROPERTY_TUNER_MODE_CAPS_S (ksmedia.h)
description: The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices.
tech.root: stream
ms.date: 03/14/2023
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
 - PKSPROPERTY_TUNER_MODE_CAPS_S
 - KSPROPERTY_TUNER_MODE_CAPS_S
---

## -description

The **KS_PROPERTY_TUNER_MODE_CAPS_S** structure describes the capabilities of TV and radio tuner devices.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field Mode

Specifies the tuner mode that the caller is requesting capability information about. It can be one of the following tuner modes from the KSPROPERTY_TUNER_MODES enumeration that is defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KSPROPERTY_TUNER_MODE_TV | Indicates that the tuner is capable of tuning analog broadcast or cable television channels. |
| KSPROPERTY_TUNER_MODE_FM_RADIO | Indicates that the tuner is capable of tuning FM radio channels. |
| KSPROPERTY_TUNER_MODE_AM_RADIO | Indicates that the tuner is capable of tuning AM radio channels. |
| KSPROPERTY_TUNER_MODE_DSS | Indicates that the tuner is capable of tuning DSS channels. |
| KSPROPERTY_TUNER_MODE_ATSC | Indicates that the tuner is capable of tuning Advanced Television Systems Committee broadcasts (Digital TV for the United States) or other digital television standard. |

### -field StandardsSupported

Describes the analog video standards supported. If **Mode** is set to KSPROPERTY_TUNER_MODE_TV, this member may be set to one or more (logically ORed) values from the [KS_AnalogVideoStandard](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard) enumeration.

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

Specifies the tuning method. This member must be set to only one of the values from the [**KS_TUNER_STRATEGY**](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_tuner_strategy) enumeration.

## -remarks

The minidriver fills in the mode capabilities for the requested tuner mode.

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_TUNER_MODE_CAPS](/windows-hardware/drivers/stream/ksproperty-tuner-mode-caps)

[**KS_AnalogVideoStandard**](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard)

[**KS_TUNER_STRATEGY**](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_tuner_strategy)

[PROPSETID_TUNER](/windows-hardware/drivers/stream/propsetid-tuner)
