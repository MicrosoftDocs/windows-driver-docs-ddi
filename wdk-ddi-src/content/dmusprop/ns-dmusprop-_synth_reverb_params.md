---
UID: NS:dmusprop._SYNTH_REVERB_PARAMS
title: _SYNTH_REVERB_PARAMS (dmusprop.h)
description: The SYNTH_REVERB_PARAMS structure contains configuration parameters.
old-location: audio\synth_reverb_params.htm
tech.root: audio
ms.assetid: 9537D56C-920E-478E-9061-C4909240D7A0
ms.date: 05/08/2018
ms.keywords: "*PSYNTH_REVERB_PARAMS, PSYNTH_REVERB_PARAMS, PSYNTH_REVERB_PARAMS structure pointer [Audio Devices], SYNTH_REVERB_PARAMS, SYNTH_REVERB_PARAMS structure [Audio Devices], _SYNTH_REVERB_PARAMS, audio.synth_reverb_params, dmusprop/PSYNTH_REVERB_PARAMS, dmusprop/SYNTH_REVERB_PARAMS"
ms.topic: struct
req.header: dmusprop.h
req.include-header: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dmusprop.h
api_name:
- SYNTH_REVERB_PARAMS
product:
- Windows
targetos: Windows
req.typenames: SYNTH_REVERB_PARAMS, *PSYNTH_REVERB_PARAMS
---

# _SYNTH_REVERB_PARAMS structure


## -description


The SYNTH_REVERB_PARAMS structure contains configuration parameters.


## -struct-fields




### -field fInGain

Specifies the input gain in decibels (dB) to avoid output overflows.


### -field fReverbMix

Specifies the reverb mix in dB. 0dB specifies 100% wet reverb (no direct signal). Negative values specify a less wet signal. The coefficients are calculated so that the overall output level stays approximately constant regardless of the amount of reverb mix. 


### -field fReverbTime

Specifies the reverb delay time in milliseconds.


### -field fHighFreqRTRatio

Specifies the ratio of the high frequencies to the global reverb time. Unless very 'splashy-bright' reverberations are desired, this should be set to a value less than 1.0. For example, if <b>dRevTime</b> is 1000ms and HHighFreqRTRatio is 0.1, then the decay time for high frequencies will be 100ms.

