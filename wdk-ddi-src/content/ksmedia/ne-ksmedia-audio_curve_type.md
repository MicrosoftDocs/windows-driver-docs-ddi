---
UID: NE:ksmedia.__unnamed_enum_125
title: AUDIO_CURVE_TYPE (ksmedia.h)
description: The AUDIO_CURVE_TYPE enumeration defines constants that specify a curve algorithm to be applied to set a volume level.
old-location: audio\audio_curve_type.htm
tech.root: audio
ms.assetid: E3CE3385-8744-4E3F-A5EF-41AC4E3E4375
ms.date: 05/21/2018
ms.keywords: AUDIO_CURVE_TYPE, AUDIO_CURVE_TYPE enumeration [Audio Devices], AUDIO_CURVE_TYPE_NONE, AUDIO_CURVE_TYPE_WINDOWS_FADE, audio.audio_curve_type, ksmedia/AUDIO_CURVE_TYPE, ksmedia/AUDIO_CURVE_TYPE_NONE, ksmedia/AUDIO_CURVE_TYPE_WINDOWS_FADE
f1_keywords:
 - "ksmedia/AUDIO_CURVE_TYPE"
req.header: ksmedia.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ksmedia.h
api_name:
- AUDIO_CURVE_TYPE
product:
- Windows
targetos: Windows
req.typenames: AUDIO_CURVE_TYPE
ms.custom: 19H1
---

# AUDIO_CURVE_TYPE enumeration

## -description

The **AUDIO_CURVE_TYPE** enumeration defines constants that specify a curve algorithm to be applied to set a volume level.

## -enum-fields

### -field AUDIO_CURVE_TYPE_NONE

Specifies that no curve algorithm will be applied.  When this curve is specified, the duration of the curve specified must be equal to 0.

### -field AUDIO_CURVE_TYPE_WINDOWS_FADE

Specifies that the algorithm that is applied to the volume setting must follow the curve shown in the diagram in the [Remarks](#remarks) section.

## -remarks

The following snippet of pseudocode shows the logic for the algorithm that is applied to the volume setting to reach the target volume level.

```cpp
// POWER IN AMPLITUDE: 1.75

// Fade In:
// Curve begins at 0 when nFrame = 0
// When nFrame gets to (nFrames - 1), curve = 1
//
// curve = pow(nFrame / (nFrames - 1), exponent)

float fFrameCount = nFrames - 1.0f;
for (UINT32 nFrame = 0; nFrame < nFrames; nFrame++) {
    float curve = powf(nFrame / fFrameCount, 1.75f);
    for (UINT32 nChannel = 0; nChannel < pWfx->nChannels; nChannel++) {
            pFloat[nFrame * pWfx->nChannels + nChannel] *= curve;
    }
}

// Fade Out:
// curve begins at 1 when nFrame = 0
// When nFrame gets to (nFrames - 1), curve = 0
//
// curve = pow(1 - (nFrame / (nFrames - 1)), exponent)

float fFrameCount = nFrames - 1.0f;
for (UINT32 nFrame = 0; nFrame < nFrames; nFrame++) {
    float curve = powf(1.0f - (nFrame / fFrameCount), 1.75f);
    for (UINT32 nChannel = 0; nChannel < pWfx->nChannels; nChannel++) {
            pFloat[nFrame * pWfx->nChannels + nChannel] *= curve;
    }
}
```

And the following diagram shows a graphical representation of the preceding pseudocode for setting the volume level.

![Graphical representation of volume level curve](../images/audio-curve-type.png)

## -see-also

[KSAUDIOENGINE_VOLUMELEVEL](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_tagksaudioengine_volumelevel)

[KSPROPERTY_AUDIOENGINE_VOLUMELEVEL](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audioengine-volumelevel)
