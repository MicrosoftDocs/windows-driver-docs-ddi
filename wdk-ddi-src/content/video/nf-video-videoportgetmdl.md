---
UID: NF:video.VideoPortGetMdl
title: VideoPortGetMdl function (video.h)
description: The VideoPortGetMdl function is obsolete in Windows 2000 and later.VideoPortGetMdl retrieves the memory descriptor list (MDL) that represents the page table of the locked buffer.
old-location: display\videoportgetmdl.htm
tech.root: display
ms.assetid: 03ec6323-a3f9-485d-80c8-92ac99d8e73a
ms.date: 05/10/2018
keywords: ["VideoPortGetMdl function"]
ms.keywords: VideoPortGetMdl, VideoPortGetMdl function [Display Devices], VideoPort_Functions_570b04cd-9b69-4d1a-b953-7220d4fc7790.xml, display.videoportgetmdl, video/VideoPortGetMdl
f1_keywords:
 - "video/VideoPortGetMdl"
 - "VideoPortGetMdl"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortGetMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetMdl function


## -description


The <b>VideoPortGetMdl</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortGetMdl</b> retrieves the memory descriptor list (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>) that represents the page table of the locked buffer.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pDma [in]

Is a handle to the DMA context being queried. This handle was obtained from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportlockpages">VideoPortLockPages</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportdodma">VideoPortDoDma</a>.


## -returns



<b>VideoPortGetMdl</b> returns <i>pDma</i>, for compatibility reasons. 




## -remarks



See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bus-master-dma-in-video-miniport-drivers">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.



