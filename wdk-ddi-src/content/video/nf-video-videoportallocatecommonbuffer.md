---
UID: NF:video.VideoPortAllocateCommonBuffer
title: VideoPortAllocateCommonBuffer function (video.h)
description: The VideoPortAllocateCommonBuffer function allocates and maps system memory so that it is simultaneously accessible from both the processor and a device for common-buffer DMA operations.
old-location: display\videoportallocatecommonbuffer.htm
tech.root: display
ms.assetid: 950c2509-688e-4aaa-a12d-4106bb722bbc
ms.date: 05/10/2018
ms.keywords: VideoPortAllocateCommonBuffer, VideoPortAllocateCommonBuffer function [Display Devices], VideoPort_Functions_bd747ea0-7963-4008-a91c-eb5598fc6bdd.xml, display.videoportallocatecommonbuffer, video/VideoPortAllocateCommonBuffer
ms.topic: function
f1_keywords:
 - "video/VideoPortAllocateCommonBuffer"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
- VideoPortAllocateCommonBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortAllocateCommonBuffer function


## -description


The <b>VideoPortAllocateCommonBuffer</b> function allocates and maps system memory so that it is simultaneously accessible from both the processor and a device for common-buffer DMA operations.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VpDmaAdapter [in]

Pointer to the <a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure was returned by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>.


### -param DesiredLength [in]

Specifies the requested number of bytes of memory.


### -param LogicalAddress [out]

Pointer to a memory location that receives the logical address to be used by the adapter to access the allocated buffer.


### -param CacheEnabled [in]

Specifies whether the allocated memory can be cached.  For more information, see the description of the <i>CacheEnabled</i> parameter for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_common_buffer">AllocateCommonBuffer</a>.


### -param Reserved [out]

Is currently ignored by the video port driver; should be set to <b>NULL</b>.


## -returns



<b>VideoPortAllocateCommonBuffer</b> returns the base virtual address of the allocated buffer if successful; otherwise, it returns <b>NULL</b> if the buffer cannot be allocated.




## -remarks



When the buffer is no longer needed, the video miniport driver should release it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportreleasecommonbuffer">VideoPortReleaseCommonBuffer</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_common_buffer">AllocateCommonBuffer</a>



<a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportreleasecommonbuffer">VideoPortReleaseCommonBuffer</a>
 

 

