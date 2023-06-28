---
UID: NA:a2dpsidebandaudio
tech.root: audio
title: a2dpsidebandaudio
ms.date: 05/20/2021
targetos: Windows
description: The a2dpsidebandaudio header defines, values, gets and sets, that are used to support A2DP sideband audio.
req.assembly: 
req.construct-type: apiset
req.ddi-compliance: 
req.dll: 
req.header: a2dpsidebandaudio.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - a2dpsidebandaudio.h
api_name:
 - a2dpsidebandaudio
f1_keywords:
 - a2dpsidebandaudio
 - a2dpsidebandaudio/a2dpsidebandaudio
dev_langs:
 - c++
---

# a2dpsidebandaudio


## -description

The a2dpsidebandaudio header defines, values, gets and sets, that are used to support A2DP sideband audio.

The following GUIDs are defined.

**GUID_DEVINTERFACE_A2DP_SIDEBAND_AUDIO**

The interface class GUID for A2DP SIDEBAND AUDIO bypass.

{F3B1362F-C9F4-4DD1-9D55-E02038A129FB}

DEFINE_GUID (GUID_DEVINTERFACE_A2DP_SIDEBAND_AUDIO,
    0xf3b1362f, 0xc9f4, 0x4dd1, 0x9d, 0x55, 0xe0, 0x20, 0x38, 0xa1, 0x29, 0xfb);

**GUID_SIDEBANDAUDIO_A2DP_SUPPORT_INTERFACE**

Published by the audio driver to indicate that it is configured for Bluetooth A2DP sideband streaming.
 
{2BC51EE4-07AF-49CF-B04B-FB3F1C26AADC}
DEFINE_GUID(GUID_SIDEBANDAUDIO_A2DP_SUPPORT_INTERFACE, 0x2bc51ee4, 0x7af, 0x49cf, 0xb0, 0x4b, 0xfb, 0x3f, 0x1c, 0x26, 0xaa, 0xdc);


**SIDEBANDAUDIO_PARAMS_SET_A2DP**

Microsoft A2DP Audio Sideband Set of Parameters

{8FE0297F-3AE6-4384-ACE3-87589E571B9C}
DEFINE_GUID(SIDEBANDAUDIO_PARAMS_SET_A2DP,
    0x8fe0297f, 0x3ae6, 0x4384, 0xac, 0xe3, 0x87, 0x58, 0x9e, 0x57, 0x1b, 0x9c);

## -remarks

## -see-also

[SET_VENDOR_ID_FROM_PARAMSET](./nf-a2dpsidebandaudio-set_vendor_id_to_paramset.md)

[GET_VENDOR_ID_FROM_PARAMSET](./nf-a2dpsidebandaudio-get_vendor_id_from_paramset.md)

[A2DPSidebandAudio](./index.md)
