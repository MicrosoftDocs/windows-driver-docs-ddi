---
UID: NE:a2dpsidebandaudio._SIDEBANDAUDIO_PARAMS_A2DP
tech.root: audio
title: SIDEBANDAUDIO_PARAMS_A2DP
description: Identifies the SIDEBANDAUDIO_PARAMS_SET_A2DP parameter.
ms.date: 05/14/2021
targetos: Windows
req.construct-type: enumeration
req.ddi-compliance: 
req.header: a2dpsidebandaudio.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - a2dpsidebandaudio.h
api_name:
 - _SIDEBANDAUDIO_PARAMS_A2DP
 - SIDEBANDAUDIO_PARAMS_A2DP
f1_keywords:
 - _SIDEBANDAUDIO_PARAMS_A2DP
 - a2dpsidebandaudio/_SIDEBANDAUDIO_PARAMS_A2DP
 - SIDEBANDAUDIO_PARAMS_A2DP
 - a2dpsidebandaudio/SIDEBANDAUDIO_PARAMS_A2DP
dev_langs:
 - c++
---

## -description

Identifies the SIDEBANDAUDIO_PARAMS_SET_A2DP parameter.

## -enum-fields

### -field SIDEBANDAUDIO_PARAM_A2DP_CODECS

Supported codecs information

The value is a sequence of Media Codec Capabilities fields as defined in table 8.52, section 8.21.5 of AVDTP 1.3. Also, see A2DP 1.3.1 section 4.2.5 and section 4.7.2 for additional information.

SIDEBANDAUDIO_PARAM_A2DP_CODECS = 1,


### -field SIDEANDAUDIO_PARAM_A2DP_CONFIGURED_CODEC

Configured codec information

The value is a single Media Codec Capabilities field as defined in table 8.52, section 8.21.5 of AVDTP 1.3.
Also, see A2DP 1.3.1 section 4.2.5 and section 4.7.2 for additional information.

SIDEANDAUDIO_PARAM_A2DP_CONFIGURED_CODEC = 2,

## -remarks

## -see-also

[A2DPSidebandAudio](/windows-hardware/drivers/ddi/a2dpsidebandaudio/)