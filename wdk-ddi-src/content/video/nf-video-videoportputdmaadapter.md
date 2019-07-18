---
UID: NF:video.VideoPortPutDmaAdapter
title: VideoPortPutDmaAdapter function (video.h)
description: The VideoPortPutDmaAdapter function frees a VP_DMA_ADAPTER structure that was previously allocated by a call to VideoPortGetDmaAdapter.
old-location: display\videoportputdmaadapter.htm
tech.root: display
ms.assetid: 80f1f1bd-57da-46b2-9967-9ba4b08ea057
ms.date: 05/10/2018
ms.keywords: VideoPortPutDmaAdapter, VideoPortPutDmaAdapter function [Display Devices], VideoPort_Functions_3de2fb91-53a9-4a1d-9dcd-91e3c0d645ab.xml, display.videoportputdmaadapter, video/VideoPortPutDmaAdapter
ms.topic: function
f1_keywords:
 - "video/VideoPortPutDmaAdapter"
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
- VideoPortPutDmaAdapter
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortPutDmaAdapter function


## -description


The <b>VideoPortPutDmaAdapter</b> function frees a <a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a> structure that was previously allocated by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VpDmaAdapter [in]

Pointer to the <a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter.


## -returns



None




## -remarks



A miniport driver should call this function only if it will not use the same VP_DMA_ADAPTER structure again.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>
 

 

