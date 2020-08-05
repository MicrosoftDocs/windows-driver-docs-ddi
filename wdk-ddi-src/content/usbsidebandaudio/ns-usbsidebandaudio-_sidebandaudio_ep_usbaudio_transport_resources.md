---
UID: NS:usbsidebandaudio._SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES
title: _SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES (usbsidebandaudio.h)
description: This structure describes USB sideband audio transport resources.
ms.assetid: 4c4691b4-9f3a-411f-b7e2-9a856c3c12b9
ms.date: 09/06/2018
keywords: ["SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES structure"]
f1_keywords:
 - "usbsidebandaudio/_SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES"
 - "_SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES"
ms.keywords: _SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES, SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES, *PSIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES, 
req.header: usbsidebandaudio.h
req.include-header: usbsidebandaudio.h
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
req.typenames: SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES, *PSIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbsidebandaudio.h
api_name: 
- _SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# _SIDEBANDAUDIO_EP_USBAUDIO_TRANSPORT_RESOURCES structure

## -description

This structure describes USB sideband audio transport resources.

## -struct-fields

### -field bcdAudioSpec
From the USB class-specific AC interface descriptor.
 
### -field bDelay
Delay introduced by the data path.
 
### -field bSlotSize
From the Audio Format Type I Descriptor.

## -remarks

## -see-also
[usbsidebandaudio.h](index.md)
