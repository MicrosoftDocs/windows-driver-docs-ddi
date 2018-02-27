---
UID: NA:dmusicks
ms.assetid: c45b3cd8-75b9-3c2a-99f7-976310a605af
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Dmusicks.h header



This header is used by Audio. For more information, see
- [Audio](../_audio/index.md)

Dmusicks.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_DMUS_KERNEL_EVENT structure](ns-dmusicks-_dmus_kernel_event.md) | The DMUS_KERNEL_EVENT structure is used to package time-stamped music events. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [DMUS_STREAM_TYPE enumeration](ne-dmusicks-dmus_stream_type.md) | Used for a DirectMusic synthesizer device. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IAllocatorMXF interface](nn-dmusicks-iallocatormxf.md) | The IAllocatorMXF interface manages buffer storage for DirectMusic streams. |
| [IMXF interface](nn-dmusicks-imxf.md) | The IMXF interface represents the DirectMusic stream on a MIDI transport filter (MXF). |
| [IMasterClock interface](nn-dmusicks-imasterclock.md) | The IMasterClock interface provides Microsoft DirectMusic streams with access to the current reference time from the master clock. |
| [IMiniportDMus interface](nn-dmusicks-iminiportdmus.md) | The IMiniportDMus interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device. |
| [IPortDMus interface](nn-dmusicks-iportdmus.md) | The IPortDMus interface is the DMus port driver's primary interface. |
| [IPositionNotify interface](nn-dmusicks-ipositionnotify.md) | PositionNotify |
| [ISynthSinkDMus interface](nn-dmusicks-isynthsinkdmus.md) | The ISynthSinkDMus interface handles wave output for a DirectMusic synthesizer device. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IAllocatorMXF::GetBuffer method](nf-dmusicks-iallocatormxf-getbuffer.md) | The GetBuffer method allocates a buffer for long MIDI events. |
| [IAllocatorMXF::GetBufferSize method](nf-dmusicks-iallocatormxf-getbuffersize.md) | The GetBufferSize method gets the buffer size from the allocator. |
| [IAllocatorMXF::GetMessage method](nf-dmusicks-iallocatormxf-getmessage.md) | The GetMessage method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse DMUS_KERNEL_EVENT structures. |
| [IAllocatorMXF::PutBuffer method](nf-dmusicks-iallocatormxf-putbuffer.md) | This method is not currently used by the miniport driver. The PutBuffer method passes a buffer to the allocator, but this occurs automatically when IMXF |
| [IMasterClock::GetTime method](nf-dmusicks-imasterclock-gettime.md) | The GetTime method retrieves the current reference time read from the master clock. |
| [IMiniportDMus::Init method](nf-dmusicks-iminiportdmus-init.md) | The Init method initializes the DMus miniport object. |
| [IMiniportDMus::NewStream method](nf-dmusicks-iminiportdmus-newstream.md) | The NewStream method creates a new instance of a logical stream associated with a specified physical channel. |
| [IMiniportDMus::Service method](nf-dmusicks-iminiportdmus-service.md) | This method does not currently need to be implemented in the miniport driver. The Service method is currently unused. |
| [IPortDMus::Notify method](nf-dmusicks-iportdmus-notify.md) | The Notify method should be called from the miniport driver's interrupt service routine (ISR) when a hardware interrupt has occurred. |
| [IPortDMus::RegisterServiceGroup method](nf-dmusicks-iportdmus-registerservicegroup.md) | The RegisterServiceGroup method registers a service group with the DMus port driver. |
| [IPositionNotify::PositionNotify method](nf-dmusicks-ipositionnotify-positionnotify.md) | Byte position notify for MXF graph. |
| [ISynthSinkDMus::RefTimeToSample method](nf-dmusicks-isynthsinkdmus-reftimetosample.md) | The RefTimeToSample method converts a reference time into a sample time. |
| [ISynthSinkDMus::Render method](nf-dmusicks-isynthsinkdmus-render.md) | The Render method renders wave data into a destination sink. |
| [ISynthSinkDMus::SampleToRefTime method](nf-dmusicks-isynthsinkdmus-sampletoreftime.md) | The SampleToRefTime method converts a sample time to a reference time. |
| [ISynthSinkDMus::SyncToMaster method](nf-dmusicks-isynthsinkdmus-synctomaster.md) | The SyncToMaster method allows synchronization to the master clock in order to avoid drift. |
