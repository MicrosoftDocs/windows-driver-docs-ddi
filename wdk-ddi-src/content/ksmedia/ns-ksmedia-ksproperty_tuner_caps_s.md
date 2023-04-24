---
UID: NS:ksmedia.KSPROPERTY_TUNER_CAPS_S
title: KSPROPERTY_TUNER_CAPS_S (ksmedia.h)
description: The KSPROPERTY_TUNER_CAPS_S structure describes the hardware capabilities of TV and radio tuning devices.
tech.root: stream
ms.date: 03/14/2023
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

## -description

The **KSPROPERTY_TUNER_CAPS_S** structure describes the hardware capabilities of TV and radio tuning devices.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field ModesSupported

Specifies a bitwise OR of the supported tuner modes. This member may be set to one or more of the following values from the KSPROPERTY_TUNER_MODES enumeration that is defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KSPROPERTY_TUNER_MODE_TV | Indicates that the tuner is capable of tuning analog broadcast or cable television channels. |
| KSPROPERTY_TUNER_MODE_FM_RADIO | Indicates that the tuner is capable of tuning FM radio channels. |
| KSPROPERTY_TUNER_MODE_AM_RADIO | Indicates that the tuner is capable of tuning AM radio channels. |
| KSPROPERTY_TUNER_MODE_DSS | Indicates that the tuner is capable of tuning DSS channels. |
| KSPROPERTY_TUNER_MODE_ATSC | Indicates that the tuner is capable of tuning digital television channels. This setting can be used for ATSC, DVB-C, or DVB-T television reception. |

### -field VideoMedium

Specifies a unique GUID representing the hardware connection of the analog video signal. This value enforces connections between filters. Possible values are **NULL**, indicating that no pin is created; GUID_NULL, indicating that Medium is not used to enforce connections; or a GUID. If a GUID value is used, only crossbar pins with a matching Medium GUID are allowed to connect.

### -field TVAudioMedium

Specifies a unique GUID representing the hardware connection of the TV audio signal. This value enforces connections between filters. Possible values are **NULL**, indicating that no pin is created; GUID_NULL, indicating that Medium is not used to enforce connections; or a GUID. If a GUID value is used, only crossbar pins with a matching Medium GUID are allowed to connect.

### -field RadioAudioMedium

Specifies a unique GUID representing the hardware connection of the analog radio audio signal. This value enforces connections between filters. Possible values are **NULL**, indicating that no pin is created; GUID_NULL, indicating that Medium is not used to enforce connections; or a GUID. If a GUID value is used, only crossbar pins with a matching Medium GUID are allowed to connect.

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_TUNER_CAPS](/windows-hardware/drivers/stream/ksproperty-tuner-caps)

[KSPROPERTY_TUNER_IF_MEDIUM](/windows-hardware/drivers/stream/ksproperty-tuner-if-medium)

[PROPSETID_TUNER](/windows-hardware/drivers/stream/propsetid-tuner)
