---
UID: NS:ksmedia.KSMIDILOOPED_BUFFER
tech.root: audio
title: KSMIDILOOPED_BUFFER (ksmedia.h)
ms.date: 10/20/2025
targetos: Windows
description: The KSMIDILOOPED_BUFFER structure describes the buffer information returned by the KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER property.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: KSMIDILOOPED_BUFFER, *PKSMIDILOOPED_BUFFER
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ms.keywords: "*PKSMIDILOOPED_BUFFER, KSMIDILOOPED_BUFFER, KSMIDILOOPED_BUFFER structure [Audio Devices], PKSMIDILOOPED_BUFFER, PKSMIDILOOPED_BUFFER structure pointer [Audio Devices], audio.ksmidilooped_buffer, ksmedia/KSMIDILOOPED_BUFFER, ksmedia/PKSMIDILOOPED_BUFFER"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSMIDILOOPED_BUFFER
 - PKSMIDILOOPED_BUFFER
f1_keywords:
 - KSMIDILOOPED_BUFFER
 - ksmedia/KSMIDILOOPED_BUFFER
 - PKSMIDILOOPED_BUFFER
 - ksmedia/PKSMIDILOOPED_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - KSMIDILOOPED_BUFFER
---

# KSMIDILOOPED_BUFFER structure

## -description

The **KSMIDILOOPED_BUFFER** structure describes the buffer information returned by the [KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER](/windows-hardware/drivers/audio/ksproperty-midiloopedstreaming-buffer) property. It contains a pointer to the cross process memory buffer mapped into the callers process space, along with the size of the buffer allocated.

## -struct-fields

### -field BufferAddress

Specifies the virtual address of the looped streaming buffer. This is the memory location where MIDI data is stored for cyclic processing.

### -field ActualBufferSize

Specifies the actual size of the allocated looped streaming buffer, in bytes. This may differ from the requested buffer size due to system constraints or alignment requirements.

## -remarks

This structure is used with the **KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER** property to retrieve information about the cyclic buffer used for MIDI looped streaming. The looped streaming mechanism allows for efficient, low-latency MIDI data processing by providing a circular buffer that can be accessed by both the driver and client applications.

The buffer address returned in *BufferAddress* is typically mapped into the client process's address space to allow direct access to the MIDI data stream.

The *ActualBufferSize* value may differ from the requested size due to hardware or alignment requirements.

## -see-also

- **[KSMIDILOOPED_BUFFER_PROPERTY](ns-ksmedia-ksmidilooped_buffer_property.md)**
- **[KSMIDILOOPED_REGISTERS](ns-ksmedia-ksmidilooped_registers.md)**
- **[KSMIDILOOPED_EVENT](ns-ksmedia-ksmidilooped_event.md)**
- **[KSPROPERTY_MIDILOOPEDSTREAMING](ne-ksmedia-ksproperty_midiloopedstreaming.md)**
