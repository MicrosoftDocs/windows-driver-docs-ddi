---
UID: NS:sidebandaudio._SIDEBANDAUDIO_VOLUME_PARAMS
title: _SIDEBANDAUDIO_VOLUME_PARAMS
author: windows-driver-content
description: Describes the endpoint index and volume value.
ms.assetid: f84929d3-f908-4686-83e7-f73e61912975
ms.author: windowsdriverdev
ms.date: 10/05/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _SIDEBANDAUDIO_VOLUME_PARAMS, SIDEBANDAUDIO_VOLUME_PARAMS, *PSIDEBANDAUDIO_VOLUME_PARAMS, 
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
req.typenames: SIDEBANDAUDIO_VOLUME_PARAMS, *PSIDEBANDAUDIO_VOLUME_PARAMS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	sidebandaudio.h
api_name: 
-	_SIDEBANDAUDIO_VOLUME_PARAMS
product: Windows
targetos: Windows
tech.root: audio
---

# _SIDEBANDAUDIO_VOLUME_PARAMS structure

## -description
Describes the endpoint index and volume value.

## -struct-fields

### -field EpIndex
 0 based index indicating the Endpoint on device.
 
### -field Immediate
Indicates whether IOCTL current value is requested or IRP should complete upon next change in value.
 
### -field Channel
0 based index indicating the channel number.

### -field Value
dbValue.

## -remarks

## -see-also
[sidebandaudio.h](index.md)
