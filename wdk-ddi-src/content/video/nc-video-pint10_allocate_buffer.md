---
UID: NC:video.PINT10_ALLOCATE_BUFFER
title: PINT10_ALLOCATE_BUFFER
author: windows-driver-content
description: The Int10AllocateBuffer function can be used to allocate a single 4 KB block of memory in the context of another thread. After the block of memory has been allocated, it must be freed before another block of memory can be allocated.
old-location: display\int10allocatebuffer.htm
tech.root: display
ms.assetid: 2e6c8000-13e3-46fb-81be-18428fec2b21
ms.date: 5/10/2018
ms.keywords: Int10AllocateBuffer, Int10AllocateBuffer callback function [Display Devices], PINT10_ALLOCATE_BUFFER, PINT10_ALLOCATE_BUFFER callback, VideoPort_Functions_9e19d07d-46a9-46ee-97db-6548202ff14f.xml, display.int10allocatebuffer, video/Int10AllocateBuffer
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	Int10AllocateBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# PINT10_ALLOCATE_BUFFER callback function


## -description


The <i>Int10AllocateBuffer</i> function can be used to allocate a single 4 KB block of memory in the context of another thread. After the block of memory has been allocated, it must be freed before another block of memory can be allocated.


## -parameters




### -param Context [in]

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a> returns.


### -param Seg [out]

Pointer to a memory location that will receive the segment address of the allocated memory buffer.


### -param Off [out]

Pointer to a memory location that will receive the offset within the segment specified by *<i>Seg</i>, of the allocated memory buffer.


### -param Length [in, out]

Pointer to a memory location that contains the length, in bytes, of the requested memory buffer, which can be as large as 4096. When the function returns, this memory location will contain the value 4096, whether the memory was actually allocated.


## -returns



The <i>Int10AllocateBuffer</i> function returns NO_ERROR upon success. It returns STATUS_INSUFFICIENT_RESOURCES if the buffer has been allocated previously or if a buffer size larger than 4096 bytes is requested. 




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a>
 

 

