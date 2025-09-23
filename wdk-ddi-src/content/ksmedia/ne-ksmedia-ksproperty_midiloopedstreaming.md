---
UID: NE:ksmedia.KSPROPERTY_MIDILOOPEDSTREAMING
tech.root: audio
title: KSPROPERTY_MIDILOOPEDSTREAMING (ksmedia.h)
ms.date: 09/22/2025
targetos: Windows
description: The KSPROPERTY_MIDILOOPEDSTREAMING enumeration defines the properties for MIDI looped streaming operations.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: KSPROPERTY_MIDILOOPEDSTREAMING
typedef_isUnnamed: false
req.umdf-ver: 
ms.keywords: "KSPROPERTY_MIDILOOPEDSTREAMING, KSPROPERTY_MIDILOOPEDSTREAMING enumeration [Audio Devices], KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER, KSPROPERTY_MIDILOOPEDSTREAMING_NOTIFICATION_EVENT, KSPROPERTY_MIDILOOPEDSTREAMING_REGISTERS, audio.ksproperty_midiloopedstreaming, ksmedia/KSPROPERTY_MIDILOOPEDSTREAMING, ksmedia/KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER, ksmedia/KSPROPERTY_MIDILOOPEDSTREAMING_NOTIFICATION_EVENT, ksmedia/KSPROPERTY_MIDILOOPEDSTREAMING_REGISTERS"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_MIDILOOPEDSTREAMING
f1_keywords:
 - KSPROPERTY_MIDILOOPEDSTREAMING
 - ksmedia/KSPROPERTY_MIDILOOPEDSTREAMING
dev_langs:
 - c++
helpviewer_keywords:
 - KSPROPERTY_MIDILOOPEDSTREAMING
---

# KSPROPERTY_MIDILOOPEDSTREAMING enumeration

## -description

The **KSPROPERTY_MIDILOOPEDSTREAMING** enumeration defines the properties available for MIDI looped streaming operations, which provide low-latency, high-performance MIDI data streaming capabilities.

## -enum-fields

### -field KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER

Specifies the property used to retrieve information about the looped streaming buffer. This property returns a [KSMIDILOOPED_BUFFER](ns-ksmedia-ksmidilooped_buffer.md) structure containing the buffer address and size. The property request uses a [KSMIDILOOPED_BUFFER_PROPERTY](ns-ksmedia-ksmidilooped_buffer_property.md) structure to specify the requested buffer size.

### -field KSPROPERTY_MIDILOOPEDSTREAMING_REGISTERS

Specifies the property used to retrieve pointers to the read and write position registers for the looped streaming buffer. This property returns a [KSMIDILOOPED_REGISTERS](ns-ksmedia-ksmidilooped_registers.md) structure containing pointers to the position registers that track the current read and write positions within the circular buffer.

### -field KSPROPERTY_MIDILOOPEDSTREAMING_NOTIFICATION_EVENT

Specifies the property used to set event handles for notifications during looped streaming operations. This property accepts a [KSMIDILOOPED_EVENT](ns-ksmedia-ksmidilooped_event.md) structure containing handles to events that will be signaled when read or write operations are completed.

## -remarks

The **KSPROPSETID_MidiLoopedStreaming** property set uses these enumeration values to identify specific properties related to MIDI looped streaming operations. Looped streaming provides a mechanism for low-latency MIDI data processing by establishing a circular buffer that is shared between the driver and client application.

The typical sequence for setting up looped streaming is:

1. Use **KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER** to allocate and retrieve buffer information
1. Use **KSPROPERTY_MIDILOOPEDSTREAMING_REGISTERS** to obtain access to position tracking registers
1. Use **KSPROPERTY_MIDILOOPEDSTREAMING_NOTIFICATION_EVENT** to configure event-based notifications

This mechanism enables high-performance MIDI applications to achieve very low latency by providing direct access to the streaming buffer and position registers.

## -see-also

- [KSMIDILOOPED_BUFFER](ns-ksmedia-ksmidilooped_buffer.md)
- [KSMIDILOOPED_BUFFER_PROPERTY](ns-ksmedia-ksmidilooped_buffer_property.md)
- [KSMIDILOOPED_REGISTERS](ns-ksmedia-ksmidilooped_registers.md)
- [KSMIDILOOPED_EVENT](ns-ksmedia-ksmidilooped_event.md)
