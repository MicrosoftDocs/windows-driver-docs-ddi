---
UID: NN:dmusicks.IAllocatorMXF
title: IAllocatorMXF
author: windows-driver-content
description: The IAllocatorMXF interface manages buffer storage for DirectMusic streams.
old-location: audio\iallocatormxf.htm
old-project: audio
ms.assetid: 4ed81d77-e140-4633-8582-d21170ecc645
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISynthSinkDMus, ISynthSinkDMus::SyncToMaster, SyncToMaster
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dmusicks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IAllocatorMXF
req.alt-loc: dmusicks.h
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
req.typenames: DMUS_STREAM_TYPE
---

# IAllocatorMXF interface



## -description
The <code>IAllocatorMXF</code> interface manages buffer storage for DirectMusic streams. The DMus port driver implements this interface and exposes it to the DMus miniport driver. The DMus port driver creates an <code>IAllocatorMXF</code> object and passes a pointer to this object to the DMus miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a> method. <code>IAllocatorMXF</code> inherits from the <a href="..\dmusicks\nn-dmusicks-imxf.md">IMXF</a> interface.

<code>IAllocatorMXF</code> is the interface through which the miniport driver communicates with the port driver's internal <a href="https://msdn.microsoft.com/8f263288-2f79-4f1d-b740-d78d40f47b32">allocator</a>, which allocates and manages the reuse of a pool of <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a> structures. Each structure can contain a time-stamped MIDI event.

The allocator also abstracts the allocation of the additional memory that is needed to store large events. The <b>uData</b> member of DMUS_KERNEL_EVENT is a union that is the size of a pointer: four bytes on a 32-bit system and eight bytes on a 64-bit system. If the data is small enough to fit in that space, then <b>uData</b> will contain the actual MIDI data. If the data for that event is larger than the 4- or 8-byte pointer, however, the <b>cbEvent</b> member indicates this fact and <b>uData</b> contains a pointer to a buffer instead of the actual MIDI data. This buffer is managed by the allocator and is a constant size for any port-driver implementation.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IAllocatorMXF</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IAllocatorMXF</b> also has these types of members:

The <b>IAllocatorMXF</b> interface has these methods.

The <code>GetBuffer</code> method allocates a buffer for long MIDI events.

The <code>GetBufferSize</code> method gets the buffer size from the allocator.

The <code>GetMessage</code> method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a> structures.


   This method is not currently used by the miniport driver. The <code>PutBuffer</code> method passes a buffer to the allocator, but this occurs automatically when <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a> is called anyway.

 


## -members
The <b>IAllocatorMXF</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536492">IAllocatorMXF::GetBuffer</a>
</td>
<td align="left" width="63%">
The <code>GetBuffer</code> method allocates a buffer for long MIDI events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536493">IAllocatorMXF::GetBufferSize</a>
</td>
<td align="left" width="63%">
The <code>GetBufferSize</code> method gets the buffer size from the allocator.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536494">IAllocatorMXF::GetMessage</a>
</td>
<td align="left" width="63%">
The <code>GetMessage</code> method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a> structures.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536495">IAllocatorMXF::PutBuffer</a>
</td>
<td align="left" width="63%">

   This method is not currently used by the miniport driver. The <code>PutBuffer</code> method passes a buffer to the allocator, but this occurs automatically when <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a> is called anyway.

</td>
</tr>
</table>The <code>GetBuffer</code> method allocates a buffer for long MIDI events.

The <code>GetBufferSize</code> method gets the buffer size from the allocator.

The <code>GetMessage</code> method serves as the retrieval point for any DirectMusic kernel-mode component that utilizes the port driver's allocator to reuse <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a> structures.


   This method is not currently used by the miniport driver. The <code>PutBuffer</code> method passes a buffer to the allocator, but this occurs automatically when <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a> is called anyway.

 


## -remarks
