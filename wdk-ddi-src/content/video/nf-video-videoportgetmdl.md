---
UID: NF:video.VideoPortGetMdl
title: VideoPortGetMdl function
author: windows-driver-content
description: The VideoPortGetMdl function is obsolete in Windows 2000 and later.VideoPortGetMdl retrieves the memory descriptor list (MDL) that represents the page table of the locked buffer.
old-location: display\videoportgetmdl.htm
old-project: display
ms.assetid: 03ec6323-a3f9-485d-80c8-92ac99d8e73a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: VideoPortGetMdl, VideoPort_Functions_570b04cd-9b69-4d1a-b953-7220d4fc7790.xml, display.videoportgetmdl, VideoPortGetMdl function [Display Devices], video/VideoPortGetMdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortGetMdl
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetMdl function


## -description


The <b>VideoPortGetMdl</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortGetMdl</b> retrieves the memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>) that represents the page table of the locked buffer.


## -syntax


````
PVOID VideoPortGetMdl(
  _In_ PVOID HwDeviceExtension,
  _In_ PDMA  pDma
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pDma [in]

Is a handle to the DMA context being queried. This handle was obtained from <a href="..\video\nf-video-videoportlockpages.md">VideoPortLockPages</a> or <a href="..\video\nf-video-videoportdodma.md">VideoPortDoDma</a>.


## -returns



<b>VideoPortGetMdl</b> returns <i>pDma</i>, for compatibility reasons. 




## -remarks



See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.



