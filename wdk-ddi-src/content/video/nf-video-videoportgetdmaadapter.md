---
UID: NF:video.VideoPortGetDmaAdapter
title: VideoPortGetDmaAdapter function (video.h)
description: The VideoPortGetDmaAdapter function returns a pointer to a VP_DMA_ADAPTER structure, which is used in subsequent calls to other DMA-related functions.
old-location: display\videoportgetdmaadapter.htm
tech.root: display
ms.assetid: e28649d3-cb4f-4589-b421-a7cdd9139e4c
ms.date: 05/10/2018
ms.keywords: VideoPortGetDmaAdapter, VideoPortGetDmaAdapter function [Display Devices], VideoPort_Functions_a45601ab-cd5a-4aed-95ec-731f09b175a4.xml, display.videoportgetdmaadapter, video/VideoPortGetDmaAdapter
ms.topic: function
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
- VideoPortGetDmaAdapter
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetDmaAdapter function


## -description


The <b>VideoPortGetDmaAdapter</b> function returns a pointer to a <b>VP_DMA_ADAPTER</b> structure, which is used in subsequent calls to other DMA-related functions.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VpDeviceDescription [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570569">VP_DEVICE_DESCRIPTION</a> structure, which describes the attributes of the physical device.


## -returns



<b>VideoPortGetDmaAdapter</b> returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure on success; if it is unsuccessful in obtaining information about the DMA adapter, it returns <b>NULL</b>.




## -remarks



The <b>VP_DMA_ADAPTER</b> structure contains attribute information about a particular DMA adapter. This structure is an opaque data type that is used internally by the video port driver.

A video miniport driver should call the video port driver's <b>VideoPortGetDmaAdapter</b> to obtain information about a DMA adapter.

```cpp
typedef struct __VP_DMA_ADAPTER* PVP_DMA_ADAPTER;
```

This structure has no public members.

This structure is available in Windows XP and later.

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570569">VP_DEVICE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570286">VideoPortCompleteDma</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570335">VideoPortPutDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570369">VideoPortStartDma</a>
 

 

