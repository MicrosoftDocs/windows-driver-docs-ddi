---
UID: NF:video.VideoPortUnlockPages
title: VideoPortUnlockPages function
author: windows-driver-content
description: The VideoPortUnlockPages function is obsolete in Windows 2000 and later. Use VideoPortUnlockBuffer in place of this function.VideoPortUnlockPages releases memory used for packet-based DMA.
old-location: display\videoportunlockpages.htm
old-project: display
ms.assetid: c233d4e1-285c-4f74-bb37-808cf855b19c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: VideoPortUnlockPages, VideoPortUnlockPages function [Display Devices], VideoPort_Functions_f7a233cf-3db5-49db-94e9-d2c6ec96f05d.xml, display.videoportunlockpages, video/VideoPortUnlockPages
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortUnlockPages
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortUnlockPages function


## -description


The <b>VideoPortUnlockPages</b> function is <b>obsolete</b> in Windows 2000 and later. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff570373">VideoPortUnlockBuffer</a> in place of this function.

<b>VideoPortUnlockPages</b> releases memory used for packet-based DMA.


## -parameters




### -param hwDeviceExtension

Pointer to the miniport driver's device extension.


### -param pDma

Specifies a non-<b>NULL</b> DMA handle. 


## -returns



<b>VideoPortUnlockPages</b> always returns <b>TRUE</b>.




## -remarks



See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.

This function can be called only within the context of a DMA IOCTL. It cannot be called from an ISR or DPC.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570373">VideoPortUnlockBuffer</a>
 

 

