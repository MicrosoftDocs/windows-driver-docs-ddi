---
UID: NS:sidebandaudio._SIDEBANDAUDIO_STREAM_STATUS_PARAMS
title: _SIDEBANDAUDIO_STREAM_STATUS_PARAMS (sidebandaudio.h)
description: Describes the endpoint index and Device Error NTSTATUS.
ms.date: 09/07/2018
keywords: ["SIDEBANDAUDIO_STREAM_STATUS_PARAMS structure"]
ms.keywords: _SIDEBANDAUDIO_STREAM_STATUS_PARAMS, SIDEBANDAUDIO_STREAM_STATUS_PARAMS, *PSIDEBANDAUDIO_STREAM_STATUS_PARAMS,
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
req.typenames: SIDEBANDAUDIO_STREAM_STATUS_PARAMS, *PSIDEBANDAUDIO_STREAM_STATUS_PARAMS
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - _SIDEBANDAUDIO_STREAM_STATUS_PARAMS
 - sidebandaudio/_SIDEBANDAUDIO_STREAM_STATUS_PARAMS
 - PSIDEBANDAUDIO_STREAM_STATUS_PARAMS
 - sidebandaudio/PSIDEBANDAUDIO_STREAM_STATUS_PARAMS
 - SIDEBANDAUDIO_STREAM_STATUS_PARAMS
 - sidebandaudio/SIDEBANDAUDIO_STREAM_STATUS_PARAMS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - _SIDEBANDAUDIO_STREAM_STATUS_PARAMS
---

# _SIDEBANDAUDIO_STREAM_STATUS_PARAMS structure


## -description

Describes the endpoint index and Device Error NTSTATUS.

## -struct-fields

### -field EpIndex

0 based index indicating the Endpoint on device.

### -field Immediate

Indicates whether IOCTL current value is requested or IRP should complete upon next change in value.

### -field Status

Indicates status of stream including cause of any failure.

## -remarks

## -see-also

[sidebandaudio.h](index.md)

