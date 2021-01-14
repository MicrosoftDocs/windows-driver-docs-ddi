---
UID: NF:dmusicks.IAllocatorMXF.GetBuffer
title: IAllocatorMXF::GetBuffer (dmusicks.h)
description: The GetBuffer method allocates a buffer for long MIDI events.
old-location: audio\iallocatormxf_getbuffer.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IAllocatorMXF::GetBuffer"]
ms.keywords: GetBuffer, GetBuffer method [Audio Devices], GetBuffer method [Audio Devices],IAllocatorMXF interface, IAllocatorMXF interface [Audio Devices],GetBuffer method, IAllocatorMXF.GetBuffer, IAllocatorMXF::GetBuffer, audio.iallocatormxf_getbuffer, audmp-routines_5abb78f4-de92-4342-877f-e7f1c15f8d8e.xml, dmusicks/IAllocatorMXF::GetBuffer
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IAllocatorMXF::GetBuffer
 - dmusicks/IAllocatorMXF::GetBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dmusicks.h
api_name:
 - IAllocatorMXF::GetBuffer
---

# IAllocatorMXF::GetBuffer


## -description

The <code>GetBuffer</code> method allocates a buffer for long MIDI events.

## -parameters

### -param ppBuffer

#### - ppbBuffer [out]

Output pointer for the buffer. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the buffer.

## -returns

<code>GetBuffer</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The miniport driver calls this method only when it needs to send large chunks of data to the capture sink. Specifically, the miniport driver uses this method whenever a component needs to package more data than can be stored in the <b>uData</b> member of <a href="/windows-hardware/drivers/ddi/dmusicks/ns-dmusicks-_dmus_kernel_event">DMUS_KERNEL_EVENT</a>.

The size of the buffer can determined by calling <a href="/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iallocatormxf-getbuffersize">IAllocatorMXF::GetBufferSize</a>. <code>GetBufferSize</code> needs to be called only once because the buffer size is constant for any allocator implementation.

## -see-also

<a href="/windows-hardware/drivers/ddi/dmusicks/ns-dmusicks-_dmus_kernel_event">DMUS_KERNEL_EVENT</a>



<a href="/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-iallocatormxf">IAllocatorMXF</a>



<a href="/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iallocatormxf-getbuffersize">IAllocatorMXF::GetBufferSize</a>

