---
UID: NS:ksmedia.KSMIDILOOPED_BUFFER_PROPERTY
tech.root: audio
title: KSMIDILOOPED_BUFFER_PROPERTY (ksmedia.h)
ms.date: 09/22/2025
targetos: Windows
description: The KSMIDILOOPED_BUFFER_PROPERTY structure specifies a property request for the looped streaming buffer and includes the requested buffer size.
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
req.typenames: KSMIDILOOPED_BUFFER_PROPERTY, *PKSMIDILOOPED_BUFFER_PROPERTY
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ms.keywords: "*PKSMIDILOOPED_BUFFER_PROPERTY, KSMIDILOOPED_BUFFER_PROPERTY, KSMIDILOOPED_BUFFER_PROPERTY structure [Audio Devices], PKSMIDILOOPED_BUFFER_PROPERTY, PKSMIDILOOPED_BUFFER_PROPERTY structure pointer [Audio Devices], audio.ksmidilooped_buffer_property, ksmedia/KSMIDILOOPED_BUFFER_PROPERTY, ksmedia/PKSMIDILOOPED_BUFFER_PROPERTY"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSMIDILOOPED_BUFFER_PROPERTY
 - PKSMIDILOOPED_BUFFER_PROPERTY
f1_keywords:
 - KSMIDILOOPED_BUFFER_PROPERTY
 - ksmedia/KSMIDILOOPED_BUFFER_PROPERTY
 - PKSMIDILOOPED_BUFFER_PROPERTY
 - ksmedia/PKSMIDILOOPED_BUFFER_PROPERTY
dev_langs:
 - c++
helpviewer_keywords:
 - KSMIDILOOPED_BUFFER_PROPERTY
---

# KSMIDILOOPED_BUFFER_PROPERTY structure

## -description

The **KSMIDILOOPED_BUFFER_PROPERTY** structure specifies a property request for the looped streaming buffer and includes the requested buffer size.

## -struct-fields

### -field Property

Specifies a [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that identifies the property set, property ID, and request type for the looped streaming buffer property.

### -field RequestedBufferSize

Specifies the requested size for the looped streaming buffer, in bytes. The driver may adjust this value based on system constraints or alignment requirements.

## -remarks

This structure is used when making a **KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER** property request. It allows the client to specify the desired buffer size for the cyclic MIDI streaming buffer. The driver uses this information to allocate an appropriate buffer and returns the actual buffer details in a [KSMIDILOOPED_BUFFER](ns-ksmedia-ksmidilooped_buffer.md) structure.

The looped streaming mechanism is designed for low-latency MIDI applications that require direct access to a cyclic buffer for efficient data processing.

## -see-also

- [KSMIDILOOPED_BUFFER](ns-ksmedia-ksmidilooped_buffer.md)
- [KSPROPERTY_MIDILOOPEDSTREAMING](ne-ksmedia-ksproperty_midiloopedstreaming.md)
- [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)
