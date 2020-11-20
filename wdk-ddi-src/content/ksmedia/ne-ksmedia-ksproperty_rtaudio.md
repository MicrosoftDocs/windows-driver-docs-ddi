---
UID: NE:ksmedia.__unnamed_enum_14
title: KSPROPERTY_RTAUDIO (ksmedia.h)
description: KSPROPERTY_RTAUDIO enumerates the properties of a WaveRT audio device.
ms.assetid: b9e2c60e-2a5f-4785-ab68-6e87a2a1385f
ms.date: 11/17/2020
keywords: ["KSPROPERTY_RTAUDIO enumeration"]
ms.keywords: KSPROPERTY_RTAUDIO, KSPROPERTY_RTAUDIO,
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
targetos: Windows
ms.custom: RS5
tech.root: stream
f1_keywords:
 - KSPROPERTY_RTAUDIO
 - ksmedia/KSPROPERTY_RTAUDIO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_RTAUDIO
---

# KSPROPERTY_RTAUDIO enumeration

## -description

**KSPROPERTY_RTAUDIO** enumerates the properties of a WaveRT audio device.

## -enum-fields

### -field KSPROPERTY_RTAUDIO_GETPOSITIONFUNCTION 

This field enumerates the <b>KSPROPERTY_RTAUDIO_GETPOSITIONFUNCTION</b> property.

### -field KSPROPERTY_RTAUDIO_BUFFER

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer">KSPROPERTY_RTAUDIO_BUFFER</a> specifies a driver-allocated cyclic buffer for audio data.

### -field KSPROPERTY_RTAUDIO_HWLATENCY 

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-hwlatency">KSPROPERTY_RTAUDIO_HWLATENCY</a> retrieves a description of the stream latency of the audio hardware and its associated data path.

### -field KSPROPERTY_RTAUDIO_POSITIONREGISTER 

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-positionregister">KSPROPERTY_RTAUDIO_POSITIONREGISTER</a> maps the position register of an audio device for a particular stream into a virtual memory location that the client can access.

### -field KSPROPERTY_RTAUDIO_CLOCKREGISTER 

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-clockregister">KSPROPERTY_RTAUDIO_CLOCKREGISTER</a> maps the wall clock register of the audio device into a virtual memory location that the client can access.

### -field KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer-with-notification">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a> specifies a driver-allocated cyclic buffer for audio data and identifies event notification requirements.

### -field KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-register-notification-event">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a> registers a user-mode event for DMA-driven event notification.

### -field KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-unregister-notification-event">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a> unregisters a user-mode event from DMA-driven event notification.

### -field KSPROPERTY_RTAUDIO_QUERY_NOTIFICATION_SUPPORT

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-query-notification-support">KSPROPERTY_RTAUDIO_QUERY_NOTIFICATION_SUPPORT</a> determines whether the audio driver can notify the client application when a process that is performed on the submitted buffer is completed.

### -field KSPROPERTY_RTAUDIO_PACKETCOUNT

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-packetcount">KSPROPERTY_RTAUDIO_PACKETCOUNT</a> returns the (1-based) count of packets completely transferred from the WaveRT buffer into hardware.

### -field KSPROPERTY_RTAUDIO_PRESENTATION_POSITION

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-presentation-position">KSPROPERTY_RTAUDIO_PRESENTATION_POSITION</a> returns stream presentation information.

### -field KSPROPERTY_RTAUDIO_GETREADPACKET

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-getreadpacket">KSPROPERTY_RTAUDIO_GETREADPACKET</a> returns information about captured audio packets.

### -field KSPROPERTY_RTAUDIO_SETWRITEPACKET

<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-setwritepacket">KSPROPERTY_RTAUDIO_SETWRITEPACKET</a> informs the driver that the OS has written valid data to the WaveRT buffer.

### -field KSPROPERTY_RTAUDIO_PACKETVREGISTER

The <b>KSPROPERTY_RTAUDIO_PACKETVREGISTER</b> returns information about the packet virtual register.

## -remarks

## -see-also

[KSPROPSETID_RTAudio](/windows-hardware/drivers/audio/kspropsetid-rtaudio)
