---
UID: NF:dmusicks.IAllocatorMXF.GetBufferSize
title: IAllocatorMXF::GetBufferSize method
author: windows-driver-content
description: The GetBufferSize method gets the buffer size from the allocator.
old-location: audio\iallocatormxf_getbuffersize.htm
old-project: audio
ms.assetid: b3a35769-a98a-40f5-bdc1-db964d2a967c
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetBufferSize method [Audio Devices], GetBufferSize method [Audio Devices], IAllocatorMXF interface, GetBufferSize,IAllocatorMXF.GetBufferSize, IAllocatorMXF, IAllocatorMXF interface [Audio Devices], GetBufferSize method, IAllocatorMXF::GetBufferSize, audio.iallocatormxf_getbuffersize, audmp-routines_5eb7fc90-4f40-4796-9c7c-2086689f1593.xml, dmusicks/IAllocatorMXF::GetBufferSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	IAllocatorMXF.GetBufferSize
product:
- Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IAllocatorMXF::GetBufferSize method


## -description


The <code>GetBufferSize</code> method gets the buffer size from the allocator.


## -parameters






#### - None


## -returns



<code>GetBufferSize</code> returns the size in bytes of the buffer.




## -remarks



<code>GetBufferSize</code> simply returns the size of the buffer that the allocator provides through the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536492">IAllocatorMXF::GetBuffer</a> call. (For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536491">IAllocatorMXF</a> introduction.) Because this is constant for any version of the port driver, <code>GetBufferSize</code> typically needs to be called only once, at the time that the stream is created.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536491">IAllocatorMXF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536492">IAllocatorMXF::GetBuffer</a>
 

 

