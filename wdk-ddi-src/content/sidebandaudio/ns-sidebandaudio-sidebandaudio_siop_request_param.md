---
UID: NS:sidebandaudio.SIDEBANDAUDIO_SIOP_REQUEST_PARAM
title: SIDEBANDAUDIO_SIOP_REQUEST_PARAM (sidebandaudio.h)
description: Describes the variable I/O parameter.
ms.date: 10/20/2021
keywords: ["SIDEBANDAUDIO_SIOP_REQUEST_PARAM structure"]
ms.keywords: SIDEBANDAUDIO_SIOP_REQUEST_PARAM, SIDEBANDAUDIO_SIOP_REQUEST_PARAM, *PSIDEBANDAUDIO_SIOP_REQUEST_PARAM,
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
req.typenames: SIDEBANDAUDIO_SIOP_REQUEST_PARAM, *PSIDEBANDAUDIO_SIOP_REQUEST_PARAM
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - PSIDEBANDAUDIO_SIOP_REQUEST_PARAM
 - sidebandaudio/PSIDEBANDAUDIO_SIOP_REQUEST_PARAM
 - SIDEBANDAUDIO_SIOP_REQUEST_PARAM
 - sidebandaudio/SIDEBANDAUDIO_SIOP_REQUEST_PARAM
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - PSIDEBANDAUDIO_SIOP_REQUEST_PARAM
 - SIDEBANDAUDIO_SIOP_REQUEST_PARAM
---

# SIDEBANDAUDIO_SIOP_REQUEST_PARAM structure


## -description

Describes the variable SIOP request parameter.

### -field .EpIndex

0 based index indicating the Endpoint on device.

### -field .RequestedSiop

The requested Siop in the form of a [SIDEBANDAUDIO_IO_PARAM_HEADER structure](ns-sidebandaudio-sidebandaudio_io_param_header.md).

### -field Alignment

Allows for byte alignment.

## -union-fields

## -remarks

#### Alignment

Allows for byte alignment.

#### EpIndex

0 based index indicating the Endpoint on device.

#### RequestedSiop

The requested Siop in the form of a [SIDEBANDAUDIO_IO_PARAM_HEADER structure](ns-sidebandaudio-sidebandaudio_io_param_header.md).

## -see-also

[sidebandaudio.h](index.md)

