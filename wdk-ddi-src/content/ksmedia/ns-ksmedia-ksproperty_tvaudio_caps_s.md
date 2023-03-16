---
UID: NS:ksmedia.KSPROPERTY_TVAUDIO_CAPS_S
title: KSPROPERTY_TVAUDIO_CAPS_S (ksmedia.h)
description: The KSPROPERTY_TVAUDIO_CAPS_S structure describes the capability of a TV audio device, such as stereo versus mono audio support and language capabilities.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_TVAUDIO_CAPS_S structure"]
ms.keywords: "*PKSPROPERTY_TVAUDIO_CAPS_S, KSPROPERTY_TVAUDIO_CAPS_S, KSPROPERTY_TVAUDIO_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_TVAUDIO_CAPS_S, PKSPROPERTY_TVAUDIO_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TVAUDIO_CAPS_S, ksmedia/PKSPROPERTY_TVAUDIO_CAPS_S, stream.ksproperty_tvaudio_caps_s, vidcapstruct_dd4243d2-9778-4dae-99e2-0d32a73ab0d4.xml"
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
req.typenames: KSPROPERTY_TVAUDIO_CAPS_S, *PKSPROPERTY_TVAUDIO_CAPS_S
f1_keywords:
 - PKSPROPERTY_TVAUDIO_CAPS_S
 - ksmedia/PKSPROPERTY_TVAUDIO_CAPS_S
 - KSPROPERTY_TVAUDIO_CAPS_S
 - ksmedia/KSPROPERTY_TVAUDIO_CAPS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_TVAUDIO_CAPS_S
 - KSPROPERTY_TVAUDIO_CAPS_S
---

## -description

The KSPROPERTY_TVAUDIO_CAPS_S structure describes the capability of a TV audio device, such as stereo versus mono audio support and language capabilities.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field Capabilities

Specifies the capabilities of the TV audio device. The minidriver returns the capabilities of the TV audio device by setting this member to one or more (logically ORed) values that are defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KS_TVAUDIO_MODE_MONO | Indicates the device supports mono audio. |
| KS_TVAUDIO_MODE_STEREO | Indicates the device supports stereo audio. |
| KS_TVAUDIO_MODE_LANG_A | Indicates the device supports a primary (default) language. |
| KS_TVAUDIO_MODE_LANG_B | Indicates the device supports a second language. |
| KS_TVAUDIO_MODE_LANG_C | Indicates the device supports a third language. |

### -field InputMedium

Reserved for system use.

### -field OutputMedium

Reserved for system use.

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_TVAUDIO_CAPS](/windows-hardware/drivers/stream/ksproperty-tvaudio-caps)

[PROPSETID_VIDCAP_TVAUDIO](/windows-hardware/drivers/stream/propsetid-vidcap-tvaudio)
