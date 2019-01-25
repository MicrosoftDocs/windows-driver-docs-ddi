---
UID: NF:video.VideoPortDoDma
title: VideoPortDoDma function (video.h)
description: The VideoPortDoDma function is obsolete in Windows 2000 and later. VideoPortDoDma causes the miniport driver's HwVidStartDma function to be called.
old-location: display\videoportdodma.htm
tech.root: display
ms.assetid: a827df55-ff88-439a-8d56-fba8212105a6
ms.date: 05/10/2018
ms.keywords: VideoPortDoDma, VideoPortDoDma function [Display Devices], VideoPort_Functions_febc78ee-355f-4689-9da9-f67f829d8a32.xml, display.videoportdodma, video/VideoPortDoDma
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
-	VideoPortDoDma
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortDoDma function


## -description


The <b>VideoPortDoDma</b> function is <b>obsolete</b> in Windows 2000 and later. 

<b>VideoPortDoDma</b> causes the miniport driver's <i>HwVidStartDma</i> function to be called.


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.

### -param pDma [in]

Specifies a non-<b>NULL</b> DMA handle. This handle was obtained from a prior call to <b>VideoPortDoDma</b> or from the <b>OutputBuffer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570547">VIDEO_REQUEST_PACKET</a> returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570327">VideoPortLockPages</a>.


### -param DmaFlags [in]

Specifies the action to be performed. This member can be one of the following values:

|Value|Meaning|
|--- |--- |
|VideoPortKeepPagesLockedVideoPortDmaInitOnly|If possible, the video port driver should keep the memory locked for subsequent DMA operation(s).|
|VideoPortUnlockAfterDma|The video port driver should unlock the memory after the DMA operation is performed.|

## -returns

<b>VideoPortDoDma</b> always returns <b>NULL</b>.

## -remarks

See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570547">VIDEO_REQUEST_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570327">VideoPortLockPages</a>
 

 

