---
UID: NC:video.PEXECUTE_DMA
title: PEXECUTE_DMA (video.h)
description: HwVidExecuteDma is a miniport driver-implemented callback routine that is responsible for retrieving physical address/length pairs from a scatter/gather list, and for programming the hardware to start the actual DMA transfer.
old-location: display\hwvidexecutedma.htm
tech.root: display
ms.assetid: 262c4b9b-fdca-4899-a635-fb273bbf4cc8
ms.date: 05/10/2018
ms.keywords: HwVidExecuteDma, HwVidExecuteDma callback function [Display Devices], PEXECUTE_DMA, PEXECUTE_DMA callback, VideoMiniport_Functions_5819a796-9dfd-41fe-9158-6ec09ac14760.xml, display.hwvidexecutedma, video/HwVidExecuteDma
ms.topic: callback
req.header: video.h
req.include-header: Video.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- video.h
api_name:
- HwVidExecuteDma
product:
- Windows
targetos: Windows
req.typenames: 
---

# PEXECUTE_DMA callback function


## -description


<i>HwVidExecuteDma</i> is a miniport driver-implemented callback routine that is responsible for retrieving physical address/length pairs from a scatter/gather list, and for programming the hardware to start the actual DMA transfer.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.


### -param VpDmaAdapter

Pointer to the <a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure was returned by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>.


### -param SGList

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_vp_scatter_gather_list">VP_SCATTER_GATHER_LIST</a> structure. The video port driver fills in the information in this structure, and passes this structure to the miniport driver.


### -param Context

Pointer to the driver-determined context passed in from <b>VideoPortStartDma</b>.


## -returns



None




## -remarks



This function is available in Windows XP and later.

If the miniport driver reports that the device does not support scatter/gather, there will be only a single element in the scatter/gather list passed to this routine. The scatter/gather list is valid until <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportcompletedma">VideoPortCompleteDma</a> is called.

The last task that the video port driver's <b>VideoPortStartDma</b> function performs is to call the miniport driver's <i>HwVidExecuteDma</i> callback routine. It is this callback that actually carries out the DMA transfer operation.

<i>HwVidExecuteDma</i> must be in nonpaged memory and must not access any pageable code or data.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_vp_scatter_gather_list">VP_SCATTER_GATHER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportcompletedma">VideoPortCompleteDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportstartdma">VideoPortStartDma</a>
 

 

