---
UID: NS:sidebandaudio._SIDEBANDAUDIO_SIDETONE_PARAMS
title: _SIDEBANDAUDIO_SIDETONE_PARAMS (sidebandaudio.h)
description: The SIDEBANDAUDIO_SIDETONE_PARAMS structure describes the endpoint index and sidetone value.
ms.date: 07/11/2023
keywords: ["SIDEBANDAUDIO_SIDETONE_PARAMS structure"]
ms.keywords: _SIDEBANDAUDIO_SIDETONE_PARAMS, SIDEBANDAUDIO_SIDETONE_PARAMS, *PSIDEBANDAUDIO_SIDETONE_PARAMS,
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
req.typenames: SIDEBANDAUDIO_SIDETONE_PARAMS, *PSIDEBANDAUDIO_SIDETONE_PARAMS
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - _SIDEBANDAUDIO_SIDETONE_PARAMS
 - sidebandaudio/_SIDEBANDAUDIO_SIDETONE_PARAMS
 - PSIDEBANDAUDIO_SIDETONE_PARAMS
 - sidebandaudio/PSIDEBANDAUDIO_SIDETONE_PARAMS
 - SIDEBANDAUDIO_SIDETONE_PARAMS
 - sidebandaudio/SIDEBANDAUDIO_SIDETONE_PARAMS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - _SIDEBANDAUDIO_SIDETONE_PARAMS
 - PSIDEBANDAUDIO_SIDETONE_PARAMS
 - SIDEBANDAUDIO_SIDETONE_PARAMS
---

# SIDEBANDAUDIO_SIDETONE_PARAMS structure

## -description

The **SIDEBANDAUDIO_SIDETONE_PARAMS** structure describes the endpoint index and sidetone value.

## -struct-fields

### -field EpIndex

0 based index indicating the Endpoint on device.

### -field Immediate

Indicates whether IOCTL current value is requested or IRP should complete upon next change in value.

### -field Channel

Sidetone Volume and Mute per channel. Set as ULONG(-1) if channel specific sidetone values are not required.

### -field Sidetone

A [SIDEBANDAUDIO_SIDETONE_DESCRIPTOR structure](ns-sidebandaudio-_sidebandaudio_sidetone_descriptor.md) that describes the Sidetone on the device.

## -remarks

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[sidebandaudio.h](index.md)

[SIDEBANDAUDIO_SIDETONE_DESCRIPTOR structure](ns-sidebandaudio-_sidebandaudio_sidetone_descriptor.md)
