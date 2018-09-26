---
UID: NS:sidebandaudio._SIDEBANDAUDIO_SIDETONE_PARAMS
title: _SIDEBANDAUDIO_SIDETONE_PARAMS
author: windows-driver-content
description: 
ms.assetid: baeba68b-d15f-469f-97f8-bd53e38fe1ea
ms.author: windowsdriverdev
ms.date: 09/06/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	sidebandaudio.h
api_name: 
-	_SIDEBANDAUDIO_SIDETONE_PARAMS
product: Windows
targetos: Windows
---

# _SIDEBANDAUDIO_SIDETONE_PARAMS structure

## -description
Describes the endpoint index and sidetone value.

## -struct-fields

### -field EpIndex
0 based index indicating the Endpoint on device.
 
### -field Immediate
Indicates whether IOCTL current value is requested or IRP should complete upon next change in value.
 
### -field Channel
 Sidetone Volume and Mute per channel. Set as ULONG(-1) if channel specific sidetone values are not required.
 
### -field Sidetone
TBD 

## -remarks

## -see-also
[sidebandaudio.h](index.md)