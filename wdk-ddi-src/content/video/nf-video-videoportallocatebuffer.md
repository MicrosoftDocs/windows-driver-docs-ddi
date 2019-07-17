---
UID: NF:video.VideoPortAllocateBuffer
title: VideoPortAllocateBuffer function (video.h)
description: The VideoPortAllocateBuffer function is obsolete in Windows 2000 and later. In its place, video miniport drivers should instead use VideoPortAllocatePool. VideoPortAllocateBuffer allocates a buffer of paged pool memory.
old-location: display\videoportallocatebuffer.htm
tech.root: display
ms.assetid: 87289ea8-f727-428d-93a1-2d3b0ab44e8b
ms.date: 05/10/2018
ms.keywords: VideoPortAllocateBuffer, VideoPortAllocateBuffer function [Display Devices], VideoPort_Functions_6e90fb68-96c2-4163-87dd-0891d2e25254.xml, display.videoportallocatebuffer, video/VideoPortAllocateBuffer
ms.topic: function
f1_keywords:
 - "video/VideoPortAllocateBuffer"
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortAllocateBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortAllocateBuffer function


## -description


The <b>VideoPortAllocateBuffer</b> function is <b>obsolete</b> in Windows 2000 and later. In its place, video miniport drivers should instead use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportallocatepool">VideoPortAllocatePool</a>. 

<b>VideoPortAllocateBuffer</b> allocates a buffer of paged pool memory.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param Size [in]

Specifies the size of the buffer to allocate, in bytes.


### -param Buffer [out]

Is the location in which the video port driver returns a pointer to a pointer to the allocated pool memory.


## -returns



<b>VideoPortAllocateBuffer</b> returns NO_ERROR when it successfully completes the allocation request, or ERROR_NOT_ENOUGH_MEMORY if it is unable to allocate a buffer of <i>Size</i> bytes. A return value of ERROR_INSUFFICIENT_BUFFER indicates that a miniport driver has exceeded its maximum allowable allocation of memory.




## -remarks



A miniport driver can use the return value of this function to determine whether the buffer allocation succeeded.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportreleasebuffer">VideoPortReleaseBuffer</a>
 

 

