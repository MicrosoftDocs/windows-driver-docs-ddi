---
UID: NE:ksmedia.KSPROPERTY_RTAUDIO
title: KSPROPERTY_RTAUDIO
author: windows-driver-content
description: KSPROPERTY_RTAUDIO enumerates the properties of a WaveRT audio device.
ms.assetid: b9e2c60e-2a5f-4785-ab68-6e87a2a1385f
ms.author: windowsdriverdev
ms.date: 9/26/2018
ms.topic: enum
ms.keywords: KSPROPERTY_RTAUDIO, KSPROPERTY_RTAUDIO, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ksmedia.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: KSPROPERTY_RTAUDIO
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ksmedia.h
api_name: 
-	KSPROPERTY_RTAUDIO
product:
-   Windows
targetos: Windows
---

# KSPROPERTY_RTAUDIO enumeration

## -description

KSPROPERTY_RTAUDIO enumerates the properties of a WaveRT audio device.

## -enum-fields

### -field KSPROPERTY_RTAUDIO_GETPOSITIONFUNCTION 

### -field KSPROPERTY_RTAUDIO_BUFFER

KSPROPERTY_RTAUDIO_BUFFER specifies a driver-allocated cyclic buffer for audio data.

### -field KSPROPERTY_RTAUDIO_HWLATENCY 

KSPROPERTY_RTAUDIO_HWLATENCY retrieves a description of the stream latency of the audio hardware and its associated data path.

### -field KSPROPERTY_RTAUDIO_POSITIONREGISTER 

KSPROPERTY_RTAUDIO_POSITIONREGISTER maps the position register of an audio device for a particular stream into a virtual memory location that the client can access.

### -field KSPROPERTY_RTAUDIO_CLOCKREGISTER 

KSPROPERTY_RTAUDIO_CLOCKREGISTER maps the wall clock register of the audio device into a virtual memory location that the client can access.

### -field KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION

KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION specifies a driver-allocated cyclic buffer for audio data and identifies event notification requirements.

### -field KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT

KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT registers a user-mode event for DMA-driven event notification.

### -field KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT

KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT unregisters a user-mode event from DMA-driven event notification.

### -field KSPROPERTY_RTAUDIO_QUERY_NOTIFICATION_SUPPORT

KSPROPERTY_RTAUDIO_QUERY_NOTIFICATION_SUPPORT determines whether the audio driver can notify the client application when a process that is performed on the submitted buffer is completed.

### -field KSPROPERTY_RTAUDIO_PACKETCOUNT

KSPROPERTY_RTAUDIO_PACKETCOUNT returns the (1-based) count of packets completely transferred from the WaveRT buffer into hardware.

### -field KSPROPERTY_RTAUDIO_PRESENTATION_POSITION

KSPROPERTY_RTAUDIO_PRESENTATION_POSITION returns stream presentation information.

### -field KSPROPERTY_RTAUDIO_GETREADPACKET

KSPROPERTY_RTAUDIO_GETREADPACKET returns information about captured audio packets.

### -field KSPROPERTY_RTAUDIO_SETWRITEPACKET

KSPROPERTY_RTAUDIO_SETWRITEPACKET informs the driver that the OS has written valid data to the WaveRT buffer.

### -field KSPROPERTY_RTAUDIO_PACKETVREGISTER 

KSPROPERTY_RTAUDIO_PACKETVREGISTER returns information about the packet virtual register.

## -remarks

## -see-also

[KSPROPSETID_RTAudio](https://docs.microsoft.com/windows-hardware/drivers/audio/kspropsetid-rtaudio)
