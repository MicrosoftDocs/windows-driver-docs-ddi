---
UID: NF:video.VideoPortSetDmaContext
title: VideoPortSetDmaContext function (video.h)
description: The VideoPortSetDmaContext function is obsolete in Windows 2000 and later.
old-location: display\videoportsetdmacontext.htm
tech.root: display
ms.assetid: 4f357612-c07d-42fe-a49f-59acec80a8bc
ms.date: 05/10/2018
keywords: ["VideoPortSetDmaContext function"]
ms.keywords: VideoPortSetDmaContext, VideoPortSetDmaContext function [Display Devices], VideoPort_Functions_8e20017f-9d32-45c9-8f68-10cc61b6591d.xml, display.videoportsetdmacontext, video/VideoPortSetDmaContext
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortSetDmaContext
 - video/VideoPortSetDmaContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortSetDmaContext
---

# VideoPortSetDmaContext function


## -description

The <b>VideoPortSetDmaContext</b> function is <b>obsolete</b> in Windows 2000 and later.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param pDma 

[out]
Pointer to a DMA handle.

### -param InstanceContext 

[in]
Pointer to the DMA context to set.

## -returns

None

## -remarks

See <a href="/windows-hardware/drivers/display/bus-master-dma-in-video-miniport-drivers">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.