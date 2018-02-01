---
UID: NF:video.VideoPortStartDma
title: VideoPortStartDma function
author: windows-driver-content
description: The VideoPortStartDma function prepares the system for a DMA operation.
old-location: display\videoportstartdma.htm
old-project: display
ms.assetid: cb78e871-6177-4141-b713-25a39c928701
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPort_Functions_b568d7ff-2e88-4afe-827b-4e54e075718c.xml, display.videoportstartdma, VideoPortStartDma function [Display Devices], VideoPortStartDma, video/VideoPortStartDma
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortStartDma
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortStartDma function


## -description


The <b>VideoPortStartDma</b> function prepares the system for a DMA operation. As soon as the appropriate resource is available, <b>VideoPortStartDma</b> creates a scatter/gather list, initializes the system resources, and calls the video miniport driver-supplied <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> routine to carry out the DMA operation.


## -syntax


````
VP_STATUS VideoPortStartDma(
  _In_    PVOID           HwDeviceExtension,
  _In_    PVP_DMA_ADAPTER VpDmaAdapter,
  _In_    PVOID           Mdl,
  _In_    ULONG           Offset,
  _Inout_ PULONG          pLength,
  _In_    PEXECUTE_DMA    ExecuteDmaRoutine,
  _In_    PVOID           Context,
  _In_    BOOLEAN         WriteToDevice
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VpDmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure is returned from a call to <a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>.


### -param Mdl [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> that describes the buffer. This pointer is returned from a call to the video port driver's <a href="..\video\nf-video-videoportlockbuffer.md">VideoPortLockBuffer</a> function.


### -param Offset [in]

Specifies the byte offset in the buffer at which the DMA operation begins. The <i>Mdl</i> parameter describes this buffer.


### -param pLength [in, out]

Pointer to a variable that specifies the requested transfer size, in bytes, and that will receive the actual size to be transferred. The variable will be updated when either of the following events occurs: <b>VideoPortStartDma</b> returns or <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> is called. It is therefore safe to read this variable from within <i>HwVidExecuteDma</i> even before <b>VideoPortStartDma</b> returns.


### -param ExecuteDmaRoutine [in]

Pointer to a miniport driver-supplied <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> callback routine. <b>VideoPortStartDma</b> calls this routine to program the hardware registers and start the actual DMA operation.


### -param Context [in]

Pointer to the driver-determined context to be passed to the miniport driver's <i>HwVidExecuteDma</i> callback routine. Since the <i>HwVidExecuteDma</i> callback routine runs at DISPATCH_LEVEL, the data that <i>Context</i> points to should be in nonpaged memory.


### -param WriteToDevice [in]

Specifies the direction of the DMA transfer. A value of <b>TRUE</b> denotes a transfer from the buffer to the device, and a value of <b>FALSE</b> denotes a transfer from the device to the buffer.


## -returns


<b>VideoPortStartDma</b> returns one of the following status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NO_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The operation was successfully carried out.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_NOT_ENOUGH_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
There are not enough system resources for this operation.

</td>
</tr>
</table> 



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
Calls the video miniport driver's <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> callback.

</li>
</ul>It is possible that not all of the requested data has been transferred, since the actual amount of memory transferred is limited by the number of map registers available to the driver. Callers of this function should inspect the actual transfer size returned at <i>pLength</i> to determine whether additional data remains to be transferred. If so, the miniport driver should call <b>VideoPortStartDma</b> (and subsequently, <a href="..\video\nf-video-videoportcompletedma.md">VideoPortCompleteDma</a>) as many times as necessary to fulfill the entire transfer request. 



## -see-also

<a href="..\video\nf-video-videoportcompletedma.md">VideoPortCompleteDma</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>

<a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>

<a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortStartDma function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

