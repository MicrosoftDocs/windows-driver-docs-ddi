---
UID: NS:sidebandaudio._SIDEBANDAUDIO_MUTE_PARAMS
title: _SIDEBANDAUDIO_MUTE_PARAMS (sidebandaudio.h)
description: Describes the endpoint index and mute value.
ms.assetid: ae031886-fe99-427e-b24e-a7ae46c33956
ms.date: 10/05/2018
keywords: ["SIDEBANDAUDIO_MUTE_PARAMS structure"]
ms.keywords: _SIDEBANDAUDIO_MUTE_PARAMS, SIDEBANDAUDIO_MUTE_PARAMS, *PSIDEBANDAUDIO_MUTE_PARAMS,
req.header: sidebandaudio.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: SIDEBANDAUDIO_MUTE_PARAMS, *PSIDEBANDAUDIO_MUTE_PARAMS
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - _SIDEBANDAUDIO_MUTE_PARAMS
 - sidebandaudio/_SIDEBANDAUDIO_MUTE_PARAMS
 - PSIDEBANDAUDIO_MUTE_PARAMS
 - sidebandaudio/PSIDEBANDAUDIO_MUTE_PARAMS
 - SIDEBANDAUDIO_MUTE_PARAMS
 - sidebandaudio/SIDEBANDAUDIO_MUTE_PARAMS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - _SIDEBANDAUDIO_MUTE_PARAMS
---

# _SIDEBANDAUDIO_MUTE_PARAMS structure


## -description

Describes the endpoint index, channel, immediate mode of operation and mute value.

## -struct-fields

### -field EpIndex

0 based index indicating the Endpoint on device.

### -field Immediate

Indicates whether IOCTL current value is requested or IRP should complete upon next change in value.

### -field Channel

0 based index indicating the channel number.

### -field Value

Boolean representing mute state:
- TRUE - Muted
- FALSE - Unmuted

## -remarks

## -see-also

[sidebandaudio.h](index.md)

[IOCTL_SBAUD_GET_MUTE_STATUS_UPDATE](./ni-sidebandaudio-ioctl_sbaud_get_mute_status_update.md)