---
UID: NS:ksmedia.KSMIDILOOPED_REGISTERS
tech.root: audio
title: KSMIDILOOPED_REGISTERS (ksmedia.h)
ms.date: 10/20/2025
targetos: Windows
description: The KSMIDILOOPED_REGISTERS structure contains pointers to the read and write position registers for MIDI looped streaming.
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
req.typenames: KSMIDILOOPED_REGISTERS, *PKSMIDILOOPED_REGISTERS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ms.keywords: "*PKSMIDILOOPED_REGISTERS, KSMIDILOOPED_REGISTERS, KSMIDILOOPED_REGISTERS structure [Audio Devices], PKSMIDILOOPED_REGISTERS, PKSMIDILOOPED_REGISTERS structure pointer [Audio Devices], audio.ksmidilooped_registers, ksmedia/KSMIDILOOPED_REGISTERS, ksmedia/PKSMIDILOOPED_REGISTERS"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSMIDILOOPED_REGISTERS
 - PKSMIDILOOPED_REGISTERS
f1_keywords:
 - KSMIDILOOPED_REGISTERS
 - ksmedia/KSMIDILOOPED_REGISTERS
 - PKSMIDILOOPED_REGISTERS
 - ksmedia/PKSMIDILOOPED_REGISTERS
dev_langs:
 - c++
helpviewer_keywords:
 - KSMIDILOOPED_REGISTERS
---

# KSMIDILOOPED_REGISTERS structure

## -description

The **KSMIDILOOPED_REGISTERS** structure contains pointers to the read and write position registers for MIDI looped streaming operations.

## -struct-fields

### -field WritePosition

Pointer to a ULONG value that indicates the current write position within the looped streaming buffer, in bytes. The driver updates this register as it places new MIDI data into the buffer.

### -field ReadPosition

Pointer to a ULONG value that indicates the current read position within the looped streaming buffer, in bytes. The client updates this register as it consumes data from the buffer.

## -remarks

This structure is returned by the **[KSPROPERTY_MIDILOOPEDSTREAMING_REGISTERS](/windows-hardware/drivers/audio/ksproperty-midiloopedstreaming-registers)** property and provides direct access to the position registers used in MIDI looped streaming. These registers enable efficient, lock-free communication between the driver and client application by providing a way to track the current read and write positions in the circular buffer.

The position registers are typically mapped into both the driver's and client's address spaces, allowing for high-performance, low-latency MIDI data streaming. The client reads from **ReadPosition** to **WritePosition**, while the driver writes from **WritePosition** onwards, wrapping around to the beginning of the buffer as needed.

Both positions are byte offsets from the beginning of the looped streaming buffer and should be accessed atomically to ensure consistency.

### Code sample

```cpp
HRESULT
    LoopedBufferCall(
        _In_ ULONG& bufferSize
    )
    {
        KSMIDILOOPED_BUFFER_PROPERTY property {0};
        KSMIDILOOPED_BUFFER buffer{0};
        ULONG propertySize {sizeof(property)};

        property.Property.Set           = KSPROPSETID_MidiLoopedStreaming; 
        property.Property.Id            = KSPROPERTY_MIDILOOPEDSTREAMING_BUFFER;       
        property.Property.Flags         = KSPROPERTY_TYPE_GET;
        property.RequestedBufferSize    = bufferSize;

        RETURN_IF_FAILED(SyncIoctl(
            m_Pin.get(),
            IOCTL_KS_PROPERTY,
            &property,
            propertySize,
            &buffer,
            sizeof(buffer),
            nullptr));

        bufferSize = buffer.ActualBufferSize;

        return S_OK;
    }
```

## -see-also

- **[KSPROPERTY_MIDILOOPEDSTREAMING_REGISTERS](/windows-hardware/drivers/audio/ksproperty-midiloopedstreaming-registers)**
- **[KSMIDILOOPED_BUFFER](ns-ksmedia-ksmidilooped_buffer.md)**
- **[KSMIDILOOPED_EVENT](ns-ksmedia-ksmidilooped_event.md)**
- **[KSPROPERTY_MIDILOOPEDSTREAMING](ne-ksmedia-ksproperty_midiloopedstreaming.md)**
