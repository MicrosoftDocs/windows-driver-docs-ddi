---
UID: NS:sidebandaudio._SIDEBANDAUDIO_DEVICE_ERROR
title: _SIDEBANDAUDIO_DEVICE_ERROR
author: windows-driver-content
description: Describes the error reported on the Device.
ms.assetid: 9c317855-e7c0-422c-b30c-93b6fa488dc7
ms.date: 09/06/2018
ms.topic: struct
ms.keywords: _SIDEBANDAUDIO_DEVICE_ERROR, SIDEBANDAUDIO_DEVICE_ERROR, *PSIDEBANDAUDIO_DEVICE_ERROR, 
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
req.typenames: SIDEBANDAUDIO_DEVICE_ERROR, *PSIDEBANDAUDIO_DEVICE_ERROR
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	sidebandaudio.h
api_name: 
-	_SIDEBANDAUDIO_DEVICE_ERROR
product: Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# _SIDEBANDAUDIO_DEVICE_ERROR structure

## -description
Describes the error reported on the Device.

## -struct-fields

### -field EpIndex
Zero based index indicating the Endpoint on device.

### -field Immediate
Indicates whether IOCTL current value is requested or IRP should complete upon next change in value. 
 
### -field Status
TBD

## -remarks

## -see-also
[sidebandaudio.h](index.md)
