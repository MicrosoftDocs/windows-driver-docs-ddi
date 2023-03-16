---
UID: NS:ksmedia.KSPROPERTY_TUNER_MODE_S
title: KSPROPERTY_TUNER_MODE_S (ksmedia.h)
description: The KSPROPERTY_TUNER_MODE_S structure describes the mode of a TV or radio tuner device.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_TUNER_MODE_S structure"]
ms.keywords: "*PKSPROPERTY_TUNER_MODE_S, KSPROPERTY_TUNER_MODE_S, KSPROPERTY_TUNER_MODE_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_MODE_S, PKSPROPERTY_TUNER_MODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_MODE_S, ksmedia/PKSPROPERTY_TUNER_MODE_S, stream.ksproperty_tuner_mode_s, vidcapstruct_fe1fe8d4-8abd-4db3-8438-ef7dddadfa5c.xml"
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
req.typenames: KSPROPERTY_TUNER_MODE_S, *PKSPROPERTY_TUNER_MODE_S
f1_keywords:
 - PKSPROPERTY_TUNER_MODE_S
 - ksmedia/PKSPROPERTY_TUNER_MODE_S
 - KSPROPERTY_TUNER_MODE_S
 - ksmedia/KSPROPERTY_TUNER_MODE_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_TUNER_MODE_S
 - KSPROPERTY_TUNER_MODE_S
---

## -description

The **KSPROPERTY_TUNER_MODE_S** structure describes the mode of a TV or radio tuner device.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field Mode

Specifies the current tuner mode. If the request is a Get request, the minidriver should return the current tuner mode. If the request is a Set request, the minidriver should switch the current tuner mode to the specified value. This member can be one of the following tuner modes from the KSPROPERTY_TUNER_MODES enumeration that is defined in *Ksmedia.h*:

| Flag | Meaning |
|---|---|
| KSPROPERTY_TUNER_MODE_TV | Indicates that the tuner is currently tuning (get) or should switch to tuning broadcast or cable television channels (set). |
| KSPROPERTY_TUNER_MODE_FM_RADIO | Indicates that the tuner is currently tuning (get) or should switch to tuning (set) FM radio channels. |
| KSPROPERTY_TUNER_MODE_AM_RADIO | Indicates that the tuner is currently tuning (get) or should switch to tuning (set) AM radio channels. |
| KSPROPERTY_TUNER_MODE_DSS | Indicates that the tuner is currently tuning (get) or should switch to tuning (set) tuning DSS channels. |
| KSPROPERTY_TUNER_MODE_ATSC | Indicates that the tuner is capable of tuning (get) or should switch to tuning (set) Advanced Television Systems Committee broadcasts (Digital TV for the United States). This setting can also be used by DVB-T and DVB-C systems. |

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_TUNER_MODE](/windows-hardware/drivers/stream/ksproperty-tuner-mode)

[PROPSETID_TUNER](/windows-hardware/drivers/stream/propsetid-tuner)
