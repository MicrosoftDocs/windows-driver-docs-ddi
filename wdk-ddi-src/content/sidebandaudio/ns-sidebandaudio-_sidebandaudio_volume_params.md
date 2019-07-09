---
UID: NS:sidebandaudio._SIDEBANDAUDIO_VOLUME_PARAMS
title: _SIDEBANDAUDIO_VOLUME_PARAMS (sidebandaudio.h)
description: Describes the endpoint index and volume value.
ms.assetid: f84929d3-f908-4686-83e7-f73e61912975
ms.date: 10/05/2018
ms.topic: struct
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
- apiref
api_type: 
- HeaderDef
api_location: 
- sidebandaudio.h
api_name: 
- _SIDEBANDAUDIO_VOLUME_PARAMS
product:
- Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# _SIDEBANDAUDIO_VOLUME_PARAMS structure

## -description
Describes the endpoint index, channel, immediate mode of operation and volume value.

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

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/sidebandaudio/ni-sidebandaudio-ioctl_sbaud_get_volume_status_update">IOCTL_SBAUD_GET_VOLUME_STATUS_UPDATE</a>
