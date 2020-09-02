---
UID: NS:ksmedia.__unnamed_struct_56
title: LOOPEDSTREAMING_POSITION_EVENT_DATA (ksmedia.h)
description: The LOOPEDSTREAMING_POSITION_EVENT_DATA structure describes a position event in a looped buffer.
old-location: audio\loopedstreaming_position_event_data.htm
tech.root: audio
ms.assetid: c9ce4ff9-1c69-40c4-8d82-d1ec4e134f34
ms.date: 04/30/2019
keywords: ["LOOPEDSTREAMING_POSITION_EVENT_DATA structure"]
ms.keywords: "*PLOOPEDSTREAMING_POSITION_EVENT_DATA, LOOPEDSTREAMING_POSITION_EVENT_DATA, LOOPEDSTREAMING_POSITION_EVENT_DATA structure [Audio Devices], PLOOPEDSTREAMING_POSITION_EVENT_DATA, PLOOPEDSTREAMING_POSITION_EVENT_DATA structure pointer [Audio Devices], aud-prop_637593e4-087a-4856-95e2-cb99f9df3d0c.xml, audio.loopedstreaming_position_event_data, ksmedia/LOOPEDSTREAMING_POSITION_EVENT_DATA, ksmedia/PLOOPEDSTREAMING_POSITION_EVENT_DATA"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: LOOPEDSTREAMING_POSITION_EVENT_DATA, *PLOOPEDSTREAMING_POSITION_EVENT_DATA
f1_keywords:
 - PLOOPEDSTREAMING_POSITION_EVENT_DATA
 - ksmedia/PLOOPEDSTREAMING_POSITION_EVENT_DATA
 - LOOPEDSTREAMING_POSITION_EVENT_DATA
 - ksmedia/LOOPEDSTREAMING_POSITION_EVENT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - LOOPEDSTREAMING_POSITION_EVENT_DATA
---

# LOOPEDSTREAMING_POSITION_EVENT_DATA structure


## -description

The LOOPEDSTREAMING_POSITION_EVENT_DATA structure describes a position event in a looped buffer.

## -struct-fields

### -field KsEventData

Specifies the type of notification that the system will send to the client when the event occurs. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a>.

### -field Position

Specifies the buffer position as a byte offset from the beginning of the looped buffer. If the size of the buffer is <i>n</i> bytes, the <b>Position</b> member must contain a value in the range 0 to <i>n</i>-1.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksevent-loopedstreaming-position">KSEVENT_LOOPEDSTREAMING_POSITION</a> event uses the LOOPEDSTREAMING_POSITION_EVENT_DATA structure. This type of event occurs only in looped buffers. A looped buffer is a data buffer for an audio stream of type <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksinterface-standard-looped-streaming">KSINTERFACE_STANDARD_LOOPED_STREAMING</a>.

The driver (typically a system component) that generates the event compares the byte offset in the <b>Position</b> member to the play cursor (in a rendering stream) or the record cursor (in a capture stream). The position event occurs when the play or record cursor passes through the specified position.

When the play or record cursor reaches the end of a looped buffer, the cursor wraps around to the beginning of the buffer, which corresponds to a byte offset of 0.

For more information about looped buffers, buffer positions, and play and record cursors, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-position-property">Audio Position Property</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/kseventsetid-loopedstreaming">KSEVENTSET_LoopedStreaming</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksevent-loopedstreaming-position">KSEVENT_LOOPEDSTREAMING_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksinterface-standard-looped-streaming">KSINTERFACE_STANDARD_LOOPED_STREAMING</a>

