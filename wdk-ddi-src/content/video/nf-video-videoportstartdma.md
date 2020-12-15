---
UID: NF:video.VideoPortStartDma
title: VideoPortStartDma function (video.h)
description: The VideoPortStartDma function prepares the system for a DMA operation.
old-location: display\videoportstartdma.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortStartDma function"]
ms.keywords: VideoPortStartDma, VideoPortStartDma function [Display Devices], VideoPort_Functions_b568d7ff-2e88-4afe-827b-4e54e075718c.xml, display.videoportstartdma, video/VideoPortStartDma
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortStartDma
 - video/VideoPortStartDma
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortStartDma
---

# VideoPortStartDma function


## -description

The <b>VideoPortStartDma</b> function prepares the system for a DMA operation. As soon as the appropriate resource is available, <b>VideoPortStartDma</b> creates a scatter/gather list, initializes the system resources, and calls the video miniport driver-supplied <a href="/windows-hardware/drivers/ddi/video/nc-video-pexecute_dma">HwVidExecuteDma</a> routine to carry out the DMA operation.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param VpDmaAdapter 

[in]
Pointer to the <a href="/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure is returned from a call to <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>.

### -param Mdl 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> that describes the buffer. This pointer is returned from a call to the video port driver's <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportlockbuffer">VideoPortLockBuffer</a> function.

### -param Offset 

[in]
Specifies the byte offset in the buffer at which the DMA operation begins. The <i>Mdl</i> parameter describes this buffer.

### -param pLength 

[in, out]
Pointer to a variable that specifies the requested transfer size, in bytes, and that will receive the actual size to be transferred. The variable will be updated when either of the following events occurs: <b>VideoPortStartDma</b> returns or <a href="/windows-hardware/drivers/ddi/video/nc-video-pexecute_dma">HwVidExecuteDma</a> is called. It is therefore safe to read this variable from within <i>HwVidExecuteDma</i> even before <b>VideoPortStartDma</b> returns.

### -param ExecuteDmaRoutine 

[in]
Pointer to a miniport driver-supplied <a href="/windows-hardware/drivers/ddi/video/nc-video-pexecute_dma">HwVidExecuteDma</a> callback routine. <b>VideoPortStartDma</b> calls this routine to program the hardware registers and start the actual DMA operation.

### -param Context 

[in]
Pointer to the driver-determined context to be passed to the miniport driver's <i>HwVidExecuteDma</i> callback routine. Since the <i>HwVidExecuteDma</i> callback routine runs at DISPATCH_LEVEL, the data that <i>Context</i> points to should be in nonpaged memory.

### -param WriteToDevice 

[in]
Specifies the direction of the DMA transfer. A value of <b>TRUE</b> denotes a transfer from the buffer to the device, and a value of <b>FALSE</b> denotes a transfer from the device to the buffer.

## -returns

<b>VideoPortStartDma</b> returns one of the following status codes:

|Return code|Description|
|--- |--- |
|NO_ERROR|The operation was successfully carried out.|
|ERROR_NOT_ENOUGH_MEMORY|There are not enough system resources for this operation.|

## -remarks

To prepare for a DMA-transfer operation, <b>VideoPortStartDma</b>:

<ul>
<li>
Flushes the memory region in the host processor's caches.

</li>
<li>
Builds a scatter/gather list.

</li>
<li>
Calls the video miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pexecute_dma">HwVidExecuteDma</a> callback.

</li>
</ul>
It is possible that not all of the requested data has been transferred, since the actual amount of memory transferred is limited by the number of map registers available to the driver. Callers of this function should inspect the actual transfer size returned at <i>pLength</i> to determine whether additional data remains to be transferred. If so, the miniport driver should call <b>VideoPortStartDma</b> (and subsequently, <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportcompletedma">VideoPortCompleteDma</a>) as many times as necessary to fulfill the entire transfer request.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pexecute_dma">HwVidExecuteDma</a>



<a href="/previous-versions/ff570570(v=vs.85)">VP_DMA_ADAPTER</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportcompletedma">VideoPortCompleteDma</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdmaadapter">VideoPortGetDmaAdapter</a>
