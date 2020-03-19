---
UID: NF:video.VideoPortReleaseCommonBuffer
title: VideoPortReleaseCommonBuffer function (video.h)
description: The VideoPortReleaseCommonBuffer function frees a common buffer that was previously allocated by VideoPortAllocateCommonBuffer.
old-location: display\videoportreleasecommonbuffer.htm
tech.root: display
ms.assetid: b3733de1-63ef-43b8-b669-dbe7e573b499
ms.date: 05/10/2018
keywords: ["VideoPortReleaseCommonBuffer function"]
ms.keywords: VideoPortReleaseCommonBuffer, VideoPortReleaseCommonBuffer function [Display Devices], VideoPort_Functions_78edd589-bea5-43e3-8658-8c6c95a1f0f7.xml, display.videoportreleasecommonbuffer, video/VideoPortReleaseCommonBuffer
f1_keywords:
 - "video/VideoPortReleaseCommonBuffer"
req.header: video.h
req.include-header: Video.h, Ntdef.h
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
- VideoPortReleaseCommonBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortReleaseCommonBuffer function


## -description


The <b>VideoPortReleaseCommonBuffer</b> function frees a common buffer that was previously allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportallocatecommonbuffer">VideoPortAllocateCommonBuffer</a>.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VpDmaAdapter [in]

Pointer to the <a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This is the structure returned after a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>.


### -param Length [in]

Specifies the number of bytes of memory to be freed.


### -param LogicalAddress [in]

Specifies the logical address of the buffer to be freed.


### -param VirtualAddress [in]

Pointer to the corresponding virtual address of the allocated memory range. This value was obtained in a prior call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportallocatecommonbuffer">VideoPortAllocateCommonBuffer</a>.


### -param CacheEnabled [in]

Indicates whether the allocated memory is cached. A value of <b>TRUE</b> indicates that the allocated memory is cached.


## -returns



None




## -remarks



The parameters passed to <b>VideoPortFreeCommonBuffer</b> must match exactly those passed to and returned from <b>VideoPortAllocateCommonBuffer</b>. A driver cannot free only part of an allocated common buffer. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportallocatecommonbuffer">VideoPortAllocateCommonBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>
 

 

