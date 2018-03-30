---
UID: NF:video.VideoPortCompleteDma
title: VideoPortCompleteDma function
author: windows-driver-content
description: The VideoPortCompleteDma function flushes any data remaining in a bus-master adapter's internal cache at the end of a DMA transfer operation, and then frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA operations.
old-location: display\videoportcompletedma.htm
old-project: display
ms.assetid: 8af5a397-7945-4f72-a253-04d227bf3ca1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortCompleteDma, VideoPortCompleteDma function [Display Devices], VideoPort_Functions_1ee3a02f-e0bb-4230-8161-957ceba37206.xml, display.videoportcompletedma, video/VideoPortCompleteDma
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortCompleteDma
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortCompleteDma function


## -description


The <b>VideoPortCompleteDma</b> function flushes any data remaining in a bus-master adapter's internal cache at the end of a DMA transfer operation, and then frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA operations.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VpDmaAdapter [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure was returned by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570312">VideoPortGetDmaAdapter</a>.


### -param VpScatterGather [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570572">VP_SCATTER_GATHER_LIST</a> structure previously passed to the miniport driver callback routine, <a href="https://msdn.microsoft.com/262c4b9b-fdca-4899-a635-fb273bbf4cc8">HwVidExecuteDma</a>.


### -param WriteToDevice [in]

Specifies the direction of the DMA transfer. A value of <b>TRUE</b> denotes a transfer from the buffer to the device, and a value of <b>FALSE</b> denotes a transfer from the device to the buffer.


## -returns



<b>VideoPortCompleteDma</b> returns NO_ERROR.




## -remarks



The video miniport driver should call <b>VideoPortCompleteDma</b> immediately to free up system resources after a DMA transfer has been completed. 

It is important to note that the scatter/gather list built by <b>VideoPortStartDma</b> becomes invalid when <b>VideoPortCompleteDma</b> is called..




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570572">VP_SCATTER_GATHER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570312">VideoPortGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570369">VideoPortStartDma</a>
 

 

