---
UID: NF:dmusicks.IAllocatorMXF.GetBufferSize
title: IAllocatorMXF::GetBufferSize (dmusicks.h)
description: The GetBufferSize method gets the buffer size from the allocator.
old-location: audio\iallocatormxf_getbuffersize.htm
tech.root: audio
ms.assetid: b3a35769-a98a-40f5-bdc1-db964d2a967c
ms.date: 05/08/2018
ms.keywords: GetBufferSize, GetBufferSize method [Audio Devices], GetBufferSize method [Audio Devices],IAllocatorMXF interface, IAllocatorMXF interface [Audio Devices],GetBufferSize method, IAllocatorMXF.GetBufferSize, IAllocatorMXF::GetBufferSize, audio.iallocatormxf_getbuffersize, audmp-routines_5eb7fc90-4f40-4796-9c7c-2086689f1593.xml, dmusicks/IAllocatorMXF::GetBufferSize
ms.topic: method
f1_keywords:
 - "dmusicks/IAllocatorMXF.GetBufferSize"
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dmusicks.h
api_name:
- IAllocatorMXF.GetBufferSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IAllocatorMXF::GetBufferSize


## -description


The <code>GetBufferSize</code> method gets the buffer size from the allocator.


## -parameters






#### - None


## -returns



<code>GetBufferSize</code> returns the size in bytes of the buffer.




## -remarks



<code>GetBufferSize</code> simply returns the size of the buffer that the allocator provides through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-iallocatormxf-getbuffer">IAllocatorMXF::GetBuffer</a> call. (For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nn-dmusicks-iallocatormxf">IAllocatorMXF</a> introduction.) Because this is constant for any version of the port driver, <code>GetBufferSize</code> typically needs to be called only once, at the time that the stream is created.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nn-dmusicks-iallocatormxf">IAllocatorMXF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-iallocatormxf-getbuffer">IAllocatorMXF::GetBuffer</a>
 

 

