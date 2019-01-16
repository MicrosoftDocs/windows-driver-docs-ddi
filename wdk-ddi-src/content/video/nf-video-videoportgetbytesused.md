---
UID: NF:video.VideoPortGetBytesUsed
title: VideoPortGetBytesUsed function
description: The VideoPortGetBytesUsed function is obsolete in Windows 2000 and later.VideoPortGetBytesUsed determines the size, in bytes, of the buffer associated with a DMA handle.
old-location: display\videoportgetbytesused.htm
tech.root: display
ms.assetid: 67fe089d-4cde-4caa-a4ad-8e879a30b516
ms.date: 05/10/2018
ms.keywords: VideoPortGetBytesUsed, VideoPortGetBytesUsed function [Display Devices], VideoPort_Functions_315c6ad1-757d-44d3-8059-d94ab407ea69.xml, display.videoportgetbytesused, video/VideoPortGetBytesUsed
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortGetBytesUsed
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetBytesUsed function


## -description


The <b>VideoPortGetBytesUsed</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortGetBytesUsed</b> determines the size, in bytes, of the buffer associated with a DMA handle.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pDma [in]

Pointer to a DMA handle. To obtain the appropriate DMA handle, use the value in the <b>OutputBuffer</b> member of the <i>pVrp</i> parameter after <a href="https://msdn.microsoft.com/library/windows/hardware/ff570327">VideoPortLockPages</a> returns. 


## -returns



<b>VideoPortGetBytesUsed</b> always returns zero.




## -remarks



See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.



