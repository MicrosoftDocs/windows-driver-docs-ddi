---
UID: NS:sidebandaudio._SIDEBANDAUDIO_SUPPORTED_FORMATS
title: _SIDEBANDAUDIO_SUPPORTED_FORMATS (sidebandaudio.h)
description: The SIDEBANDAUDIO_SUPPORTED_FORMATS structure describes the formats supported by the Audio Endpoint.
ms.date: 07/11/2023
keywords: ["SIDEBANDAUDIO_SUPPORTED_FORMATS structure"]
ms.keywords: _SIDEBANDAUDIO_SUPPORTED_FORMATS, SIDEBANDAUDIO_SUPPORTED_FORMATS, *PSIDEBANDAUDIO_SUPPORTED_FORMATS,
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
req.typenames: SIDEBANDAUDIO_SUPPORTED_FORMATS, *PSIDEBANDAUDIO_SUPPORTED_FORMATS
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - _SIDEBANDAUDIO_SUPPORTED_FORMATS
 - sidebandaudio/_SIDEBANDAUDIO_SUPPORTED_FORMATS
 - PSIDEBANDAUDIO_SUPPORTED_FORMATS
 - sidebandaudio/PSIDEBANDAUDIO_SUPPORTED_FORMATS
 - SIDEBANDAUDIO_SUPPORTED_FORMATS
 - sidebandaudio/SIDEBANDAUDIO_SUPPORTED_FORMATS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - _SIDEBANDAUDIO_SUPPORTED_FORMATS
 - PSIDEBANDAUDIO_SUPPORTED_FORMATS
 - SIDEBANDAUDIO_SUPPORTED_FORMATS
---

# SIDEBANDAUDIO_SUPPORTED_FORMATS structure

## -description

The **SIDEBANDAUDIO_SUPPORTED_FORMATS** structure describes the formats supported by the Audio Endpoint.

## -struct-fields

### -field CbSize

Size of structure including storage for Formats Array allocated after the struct.

### -field EpIndex

 0 based index indicating the Endpoint on device.

### -field NumFormats

Number of KSDATAFORMAT structures.

### -field Formats

Array of pointers of KSDATAFORMAT.

## -remarks

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[sidebandaudio.h](index.md)

[IOCTL_SBAUD_GET_SUPPORTED_FORMATS](./ni-sidebandaudio-ioctl_sbaud_get_supported_formats.md)
