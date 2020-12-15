---
UID: NF:dmusicks.IAllocatorMXF.PutBuffer
title: IAllocatorMXF::PutBuffer (dmusicks.h)
description: This method is not currently used by the miniport driver. The PutBuffer method passes a buffer to the allocator, but this occurs automatically when IMXF::PutMessage is called anyway.
old-location: audio\iallocatormxf_putbuffer.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IAllocatorMXF::PutBuffer"]
ms.keywords: IAllocatorMXF interface [Audio Devices],PutBuffer method, IAllocatorMXF.PutBuffer, IAllocatorMXF::PutBuffer, PutBuffer, PutBuffer method [Audio Devices], PutBuffer method [Audio Devices],IAllocatorMXF interface, audio.iallocatormxf_putbuffer, audmp-routines_8afbc000-69b1-45a5-8fe3-3f6ff8d5518d.xml, dmusicks/IAllocatorMXF::PutBuffer
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
 - IAllocatorMXF::PutBuffer
 - dmusicks/IAllocatorMXF::PutBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dmusicks.h
api_name:
 - IAllocatorMXF.PutBuffer
---

# IAllocatorMXF::PutBuffer


## -description

   This method is not currently used by the miniport driver. The <code>PutBuffer</code> method passes a buffer to the allocator, but this occurs automatically when <a href="/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-imxf-putmessage">IMXF::PutMessage</a> is called anyway.

## -parameters

### -param pBuffer

#### - pbBuffer [in]

Pointer to the buffer being passed to the allocator

## -returns

<code>PutBuffer</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The miniport driver does not need to use this method because when the miniport driver calls <a href="/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-imxf-putmessage">IMXF::PutMessage</a>, the allocator looks at the <b>cbEvent</b> member of the <a href="/windows-hardware/drivers/ddi/dmusicks/ns-dmusicks-_dmus_kernel_event">DMUS_KERNEL_EVENT</a> structure to determine if <b>uData</b> is a pointer or just data. If <b>cbEvent</b> specifies that the event data is greater than the storage capacity of <b>uData</b> (4 bytes on a 32-bit system and 8 bytes on a 64-bit system), the allocator simply assumes that <b>uData</b> points to a buffer that can be reused.

## -see-also

<a href="/windows-hardware/drivers/ddi/dmusicks/ns-dmusicks-_dmus_kernel_event">DMUS_KERNEL_EVENT</a>



<a href="/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-iallocatormxf">IAllocatorMXF</a>



<a href="/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-imxf-putmessage">IMXF::PutMessage</a>
