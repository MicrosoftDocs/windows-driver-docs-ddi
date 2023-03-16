---
UID: NS:ksmedia.KSPROPERTY_TVAUDIO_S
title: KSPROPERTY_TVAUDIO_S (ksmedia.h)
description: The KSPROPERTY_TVAUDIO_S structure describes the current TV audio mode, such as stereo or mono audio and language settings.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_TVAUDIO_S structure"]
ms.keywords: "*PKSPROPERTY_TVAUDIO_S, KSPROPERTY_TVAUDIO_S, KSPROPERTY_TVAUDIO_S structure [Streaming Media Devices], PKSPROPERTY_TVAUDIO_S, PKSPROPERTY_TVAUDIO_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TVAUDIO_S, ksmedia/PKSPROPERTY_TVAUDIO_S, stream.ksproperty_tvaudio_s, vidcapstruct_d9dd7c2c-ed79-4efa-ae11-07e069abda5c.xml"
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
req.typenames: KSPROPERTY_TVAUDIO_S, *PKSPROPERTY_TVAUDIO_S
f1_keywords:
 - PKSPROPERTY_TVAUDIO_S
 - ksmedia/PKSPROPERTY_TVAUDIO_S
 - KSPROPERTY_TVAUDIO_S
 - ksmedia/KSPROPERTY_TVAUDIO_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_TVAUDIO_S
 - KSPROPERTY_TVAUDIO_S
---

## -description

The **KSPROPERTY_TVAUDIO_S** structure describes the current TV audio mode, such as stereo or mono audio and language settings.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field Mode

Specifies the mode of the TV audio device. For Get requests, the minidriver returns the current mode of the TV audio device. For Set requests, the minidriver sets the current mode of the TV audio device to the specified value. This member can be one or more (logically ORed) of the following values:

| Mode | Meaning |
|---|---|
| KS_TVAUDIO_MODE_MONO | Indicates that the audio is in mono. |
| KS_TVAUDIO_MODE_STEREO | Indicates that the audio is in stereo. |
| KS_TVAUDIO_MODE_LANG_A | Indicates that the audio is in the primary language. |
| KS_TVAUDIO_MODE_LANG_B | Indicates that the audio is in the second language supported by the device. |
| KS_TVAUDIO_MODE_LANG_C | Indicates that the audio is in the third language supported by the device. |

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_TVAUDIO_MODE](/windows-hardware/drivers/stream/ksproperty-tvaudio-mode)

[PROPSETID_VIDCAP_TVAUDIO](/windows-hardware/drivers/stream/propsetid-vidcap-tvaudio)
