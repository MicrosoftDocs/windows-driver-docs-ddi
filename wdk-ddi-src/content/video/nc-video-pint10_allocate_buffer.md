---
UID: NC:video.PINT10_ALLOCATE_BUFFER
title: PINT10_ALLOCATE_BUFFER
author: windows-driver-content
description: The Int10AllocateBuffer function can be used to allocate a single 4 KB block of memory in the context of another thread. After the block of memory has been allocated, it must be freed before another block of memory can be allocated.
old-location: display\int10allocatebuffer.htm
old-project: display
ms.assetid: 2e6c8000-13e3-46fb-81be-18428fec2b21
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.int10allocatebuffer, Int10AllocateBuffer callback function [Display Devices], Int10AllocateBuffer, PINT10_ALLOCATE_BUFFER, PINT10_ALLOCATE_BUFFER, video/Int10AllocateBuffer, VideoPort_Functions_9e19d07d-46a9-46ee-97db-6548202ff14f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	video.h
apiname: 
-	Int10AllocateBuffer
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PINT10_ALLOCATE_BUFFER callback


## -description


The <i>Int10AllocateBuffer</i> function can be used to allocate a single 4 KB block of memory in the context of another thread. After the block of memory has been allocated, it must be freed before another block of memory can be allocated.


## -prototype


````
PINT10_ALLOCATE_BUFFER Int10AllocateBuffer;

VP_STATUS Int10AllocateBuffer(
  _In_    PVOID   Context,
  _Out_   PUSHORT Seg,
  _Out_   PUSHORT Off,
  _Inout_ PULONG  Length
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a> returns.


### -param Seg [out]

Pointer to a memory location that will receive the segment address of the allocated memory buffer.


### -param Off [out]

Pointer to a memory location that will receive the offset within the segment specified by *<i>Seg</i>, of the allocated memory buffer.


### -param Length [in, out]

Pointer to a memory location that contains the length, in bytes, of the requested memory buffer, which can be as large as 4096. When the function returns, this memory location will contain the value 4096, whether the memory was actually allocated.


## -returns


The <i>Int10AllocateBuffer</i> function returns NO_ERROR upon success. It returns STATUS_INSUFFICIENT_RESOURCES if the buffer has been allocated previously or if a buffer size larger than 4096 bytes is requested. 



## -remarks


The video port implements this function, which can be accessed through a pointer in the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure.



## -see-also

<a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PINT10_ALLOCATE_BUFFER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

