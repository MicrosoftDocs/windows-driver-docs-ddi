---
UID: NS:sidebandaudio._SIDEBANDAUDIO_CONNECTION_PARAMS
title: _SIDEBANDAUDIO_CONNECTION_PARAMS (sidebandaudio.h)
description: Describes the endpoint index and Connection value.
ms.assetid: 15577347-4c95-4cd7-bb77-8341dbb0bae4
ms.date: 09/06/2018
ms.topic: struct
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	sidebandaudio.h
api_name: 
-	_SIDEBANDAUDIO_CONNECTION_PARAMS
product: Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# _SIDEBANDAUDIO_CONNECTION_PARAMS structure

## -description
Describes the endpoint index and Connection value.

## -struct-fields

### -field EpIndex
0 based index indicating the Endpoint on device.
 
### -field Immediate
Indicates whether IOCTL current value is requested or IRP should complete upon next change in value.

### -field Connected
Indicates whether the endpoint is connected or not. Could reflect jack states or wireless connection. 

## -remarks

## -see-also
[sidebandaudio.h](index.md)
