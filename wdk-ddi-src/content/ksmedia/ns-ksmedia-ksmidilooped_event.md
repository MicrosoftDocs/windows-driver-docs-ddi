---
UID: NS:ksmedia.KSMIDILOOPED_EVENT
tech.root: audio
title: KSMIDILOOPED_EVENT (ksmedia.h)
ms.date: 10/20/2025
targetos: Windows
description: The KSMIDILOOPED_EVENT structure specifies the event handles used for notification in MIDI looped streaming.
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
req.typenames: KSMIDILOOPED_EVENT, *PKSMIDILOOPED_EVENT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ms.keywords: "*PKSMIDILOOPED_EVENT, KSMIDILOOPED_EVENT, KSMIDILOOPED_EVENT structure [Audio Devices], PKSMIDILOOPED_EVENT, PKSMIDILOOPED_EVENT structure pointer [Audio Devices], audio.ksmidilooped_event, ksmedia/KSMIDILOOPED_EVENT, ksmedia/PKSMIDILOOPED_EVENT"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSMIDILOOPED_EVENT
 - PKSMIDILOOPED_EVENT
f1_keywords:
 - KSMIDILOOPED_EVENT
 - ksmedia/KSMIDILOOPED_EVENT
 - PKSMIDILOOPED_EVENT
 - ksmedia/PKSMIDILOOPED_EVENT
dev_langs:
 - c++
helpviewer_keywords:
 - KSMIDILOOPED_EVENT
---

# KSMIDILOOPED_EVENT structure

## -description

The **KSMIDILOOPED_EVENT** structure specifies the event handles used for notification in MIDI looped streaming operations.

## -struct-fields

### -field WriteEvent

Handle to the event that is signaled when the driver has completed a write operation to the looped streaming buffer. This event is used to synchronize data writing operations between the client and the driver.

## -remarks

This structure is used with the **KSPROPERTY_MIDILOOPEDSTREAMING_NOTIFICATION_EVENT** property to configure event-based notification for MIDI looped streaming operations. The structure provides a mechanism for efficient, low-latency communication between the MIDI driver and client applications.

The write event is typically signaled when the driver has processed data from the buffer, indicating that buffer space is available for new data. The client should create this event before setting the property, and it should be a reset event (manual or automatic reset, depending on the application's needs).

### Code sample

```cpp
_Use_decl_annotations_
NTSTATUS StreamEngine::SetLoopedStreamingNotificationEvent(PKSMIDILOOPED_EVENT Buffer)
{
 // Code to handle event...
}
```

## -see-also

- **[KSMIDILOOPED_BUFFER](ns-ksmedia-ksmidilooped_buffer.md)**
- **[KSMIDILOOPED_REGISTERS](ns-ksmedia-ksmidilooped_registers.md)**
- **[KSPROPERTY_MIDILOOPEDSTREAMING](ne-ksmedia-ksproperty_midiloopedstreaming.md)**
