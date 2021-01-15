---
UID: NS:ksmedia.__unnamed_struct_72
title: KSAC3_DIALOGUE_LEVEL (ksmedia.h)
description: The KSAC3_DIALOGUE_LEVEL structure specifies the average volume level of spoken dialog within the audio program encoded in an AC-3 stream.
old-location: audio\ksac3_dialogue_level.htm
tech.root: audio
ms.date: 08/20/2020
keywords: ["KSAC3_DIALOGUE_LEVEL structure"]
ms.keywords: "*PKSAC3_DIALOGUE_LEVEL, KSAC3_DIALOGUE_LEVEL, KSAC3_DIALOGUE_LEVEL structure [Audio Devices], PKSAC3_DIALOGUE_LEVEL, PKSAC3_DIALOGUE_LEVEL structure pointer [Audio Devices], aud-prop_223d9fe5-3b60-46b4-a157-7ddab97a75f8.xml, audio.ksac3_dialogue_level, ksmedia/KSAC3_DIALOGUE_LEVEL, ksmedia/PKSAC3_DIALOGUE_LEVEL"
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
req.typenames: KSAC3_DIALOGUE_LEVEL, *PKSAC3_DIALOGUE_LEVEL
f1_keywords:
 - PKSAC3_DIALOGUE_LEVEL
 - ksmedia/PKSAC3_DIALOGUE_LEVEL
 - KSAC3_DIALOGUE_LEVEL
 - ksmedia/KSAC3_DIALOGUE_LEVEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSAC3_DIALOGUE_LEVEL
 - KSAC3_DIALOGUE_LEVEL
---

# KSAC3_DIALOGUE_LEVEL structure


## -description

The KSAC3_DIALOGUE_LEVEL structure specifies the average volume level of spoken dialog within the audio program encoded in an AC-3 stream.

## -struct-fields

### -field DialogueLevel

Specifies how far the average dialog level is below digital 100 percent. Valid values are 1 through 31. The values 1 through 31 are interpreted as -1 decibels through -31 decibels with respect to digital 100 percent.

## -remarks

This structure is used by the [KSPROPERTY_AC3_BIT_STREAM_MODE](/windows-hardware/drivers/audio/ksproperty-ac3-bit-stream-mode) property.

For more information about bit stream modes, see the AC-3 specification at the [Dolby Laboratories](https://www.dolby.com) website. The specification is titled Digital Audio Compression Standard (AC-3).

## -see-also

[KSPROPERTY_AC3_BIT_STREAM_MODE](/windows-hardware/drivers/audio/ksproperty-ac3-bit-stream-mode)

