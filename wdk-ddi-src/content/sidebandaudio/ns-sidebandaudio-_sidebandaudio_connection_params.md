---
UID: NS:sidebandaudio._SIDEBANDAUDIO_CONNECTION_PARAMS
title: _SIDEBANDAUDIO_CONNECTION_PARAMS (sidebandaudio.h)
description: The SIDEBANDAUDIO_CONNECTION_PARAMS structure describes the endpoint index and connection value.
ms.date: 07/11/2023
keywords: ["SIDEBANDAUDIO_CONNECTION_PARAMS structure"]
ms.keywords: _SIDEBANDAUDIO_CONNECTION_PARAMS, SIDEBANDAUDIO_CONNECTION_PARAMS, *PSIDEBANDAUDIO_CONNECTION_PARAMS,
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
req.typenames: SIDEBANDAUDIO_CONNECTION_PARAMS, *PSIDEBANDAUDIO_CONNECTION_PARAMS
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - _SIDEBANDAUDIO_CONNECTION_PARAMS
 - sidebandaudio/_SIDEBANDAUDIO_CONNECTION_PARAMS
 - PSIDEBANDAUDIO_CONNECTION_PARAMS
 - sidebandaudio/PSIDEBANDAUDIO_CONNECTION_PARAMS
 - SIDEBANDAUDIO_CONNECTION_PARAMS
 - sidebandaudio/SIDEBANDAUDIO_CONNECTION_PARAMS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - _SIDEBANDAUDIO_CONNECTION_PARAMS
 - PSIDEBANDAUDIO_CONNECTION_PARAMS
 - SIDEBANDAUDIO_CONNECTION_PARAMS
---

# SIDEBANDAUDIO_CONNECTION_PARAMS structure

## -description

The **SIDEBANDAUDIO_CONNECTION_PARAMS** structure describes the endpoint index and connection value.

## -struct-fields

### -field EpIndex

0 based index indicating the Endpoint on device.

### -field Immediate

Indicates whether IOCTL current value is requested or IRP should complete upon next change in value.

### -field Connected

Indicates whether the endpoint is connected or not. Could reflect jack states or wireless connection.

## -remarks

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[sidebandaudio.h](index.md)
