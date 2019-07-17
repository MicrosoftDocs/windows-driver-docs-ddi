---
UID: NS:sidebandaudio.__unnamed_union_2
title: SIDEBANDAUDIO_STREAM_OPEN_PARAMS (sidebandaudio.h)
description: Describes the variable I/O parameters for IOCTLs.
ms.assetid: f34ee0ff-8e4a-4893-90f8-5dcf6fa50f0d
ms.date: 09/07/2018
ms.topic: struct
f1_keywords:
 - "sidebandaudio/SIDEBANDAUDIO_STREAM_OPEN_PARAMS"
ms.keywords: SIDEBANDAUDIO_STREAM_OPEN_PARAMS, SIDEBANDAUDIO_STREAM_OPEN_PARAMS, *PSIDEBANDAUDIO_STREAM_OPEN_PARAMS, 
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
req.typenames: SIDEBANDAUDIO_STREAM_OPEN_PARAMS, *PSIDEBANDAUDIO_STREAM_OPEN_PARAMS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- sidebandaudio.h
api_name: 
- SIDEBANDAUDIO_STREAM_OPEN_PARAMS
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# SIDEBANDAUDIO_STREAM_OPEN_PARAMS structure

## -description
Describes the variable I/O parameters for IOCTLs.

## -struct-fields

### -field EpIndex
0 based index indicating the Endpoint on device.

### -field Format
Stream Format KSDATAFORMAT.

### -field SiopCount
Number of Input parameters.
 
### -field Alignment
TBD 

## -remarks

## -see-also
[sidebandaudio.h](index.md)
