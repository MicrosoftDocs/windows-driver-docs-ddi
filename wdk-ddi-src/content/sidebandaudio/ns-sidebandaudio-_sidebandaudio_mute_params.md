---
UID: NS:sidebandaudio._SIDEBANDAUDIO_MUTE_PARAMS
title: _SIDEBANDAUDIO_MUTE_PARAMS
author: windows-driver-content
description: 
ms.assetid: ae031886-fe99-427e-b24e-a7ae46c33956
ms.author: windowsdriverdev
ms.date: 09/06/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	sidebandaudio.h
api_name: 
-	_SIDEBANDAUDIO_MUTE_PARAMS
product: Windows
targetos: Windows
---

# _SIDEBANDAUDIO_MUTE_PARAMS structure

## -description
Describes the endpoint index and mute value.


## -struct-fields

### -field EpIndex
0 based index indicating the Endpoint on device.
 
### -field Immediate
Indicates whether IOCTL current value is requested or IRP should complete upon next change in value
 
### -field Channel
TBD

### -field Value
TBD 

## -remarks

## -see-also
[sidebandaudio.h](index.md)