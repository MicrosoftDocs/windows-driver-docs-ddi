---
UID: NF:video.VideoPortSignalDmaComplete
title: VideoPortSignalDmaComplete function (video.h)
description: The VideoPortSignalDmaComplete function is obsolete in Windows 2000 and later.VideoPortSignalDmaComplete indicates to the video miniport driver whether the current DMA transfer is complete.
old-location: display\videoportsignaldmacomplete.htm
tech.root: display
ms.assetid: 81730acb-ff15-438d-8225-125283f61db2
ms.date: 05/10/2018
ms.keywords: VideoPortSignalDmaComplete, VideoPortSignalDmaComplete function [Display Devices], VideoPort_Functions_2246061c-11be-4eca-94bf-3b788dddd420.xml, display.videoportsignaldmacomplete, video/VideoPortSignalDmaComplete
ms.topic: function
f1_keywords:
 - "video/VideoPortSignalDmaComplete"
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
- VideoPortSignalDmaComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortSignalDmaComplete function


## -description


The <b>VideoPortSignalDmaComplete</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortSignalDmaComplete</b> indicates to the video miniport driver whether the current DMA transfer is complete.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pDmaHandle [in]

Pointer to a DMA handle. To obtain the appropriate DMA handle, use the value in the <b>OutputBuffer</b> member of the <i>pVrp</i> parameter after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportlockpages">VideoPortLockPages</a> returns. 


## -returns



<b>VideoPortSignalDmaComplete</b> always returns <b>FALSE</b>.




## -remarks



See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bus-master-dma-in-video-miniport-drivers">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.



