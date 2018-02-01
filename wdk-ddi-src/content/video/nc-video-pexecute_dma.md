---
UID: NC:video.PEXECUTE_DMA
title: PEXECUTE_DMA
author: windows-driver-content
description: HwVidExecuteDma is a miniport driver-implemented callback routine that is responsible for retrieving physical address/length pairs from a scatter/gather list, and for programming the hardware to start the actual DMA transfer.
old-location: display\hwvidexecutedma.htm
old-project: display
ms.assetid: 262c4b9b-fdca-4899-a635-fb273bbf4cc8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.hwvidexecutedma, HwVidExecuteDma callback function [Display Devices], HwVidExecuteDma, PEXECUTE_DMA, PEXECUTE_DMA, video/HwVidExecuteDma, VideoMiniport_Functions_5819a796-9dfd-41fe-9158-6ec09ac14760.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	video.h
apiname:
-	HwVidExecuteDma
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PEXECUTE_DMA callback


## -description


<i>HwVidExecuteDma</i> is a miniport driver-implemented callback routine that is responsible for retrieving physical address/length pairs from a scatter/gather list, and for programming the hardware to start the actual DMA transfer.


## -prototype


````
PEXECUTE_DMA HwVidExecuteDma;

VOID HwVidExecuteDma(
   PVOID                   HwDeviceExtension,
   PVP_DMA_ADAPTER         VpDmaAdapter,
   PVP_SCATTER_GATHER_LIST SGList,
   PVOID                   Context
)
{ ... }
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param VpDmaAdapter

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure was returned by a call to <a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>.


### -param SGList

Pointer to a <a href="..\video\ns-video-_vp_scatter_gather_list.md">VP_SCATTER_GATHER_LIST</a> structure. The video port driver fills in the information in this structure, and passes this structure to the miniport driver.


### -param Context

Pointer to the driver-determined context passed in from <b>VideoPortStartDma</b>.


## -returns


None



## -remarks


This function is available in Windows XP and later.

If the miniport driver reports that the device does not support scatter/gather, there will be only a single element in the scatter/gather list passed to this routine. The scatter/gather list is valid until <a href="..\video\nf-video-videoportcompletedma.md">VideoPortCompleteDma</a> is called.

The last task that the video port driver's <b>VideoPortStartDma</b> function performs is to call the miniport driver's <i>HwVidExecuteDma</i> callback routine. It is this callback that actually carries out the DMA transfer operation.

<i>HwVidExecuteDma</i> must be in nonpaged memory and must not access any pageable code or data.



## -see-also

<a href="..\video\nf-video-videoportstartdma.md">VideoPortStartDma</a>

<a href="..\video\nf-video-videoportcompletedma.md">VideoPortCompleteDma</a>

<a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>

<a href="..\video\ns-video-_vp_scatter_gather_list.md">VP_SCATTER_GATHER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PEXECUTE_DMA callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

