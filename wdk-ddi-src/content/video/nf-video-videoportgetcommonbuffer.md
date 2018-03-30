---
UID: NF:video.VideoPortGetCommonBuffer
title: VideoPortGetCommonBuffer function
author: windows-driver-content
description: The VideoPortGetCommonBuffer function is obsolete in Windows XP and later, and is supported only for backward compatibility with existing drivers.
old-location: display\videoportgetcommonbuffer.htm
old-project: display
ms.assetid: c8329d26-fb6f-46f1-aacd-ba78ee4ea5d5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortGetCommonBuffer, VideoPortGetCommonBuffer function [Display Devices], VideoPort_Functions_eead14aa-271b-49a2-8ded-482ffc73741e.xml, display.videoportgetcommonbuffer, video/VideoPortGetCommonBuffer
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortGetCommonBuffer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetCommonBuffer function


## -description


The <b>VideoPortGetCommonBuffer</b> function is <b>obsolete</b> in Windows XP and later, and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff570178">VideoPortAllocateCommonBuffer</a>.

<b>VideoPortGetCommonBuffer</b> allocates and maps system memory so that it is simultaneously accessible from both the processor and a device for common-buffer DMA operations.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param DesiredLength [in]

Specifies the requested number of bytes of memory.


### -param Alignment [in]

Specifies the requested alignment of the buffer. The video port driver currently ignores this parameter.


### -param LogicalAddress [out]

Pointer to a variable that receives the logical address to be used by the adapter to access the allocated buffer.


### -param pActualLength [out]

Pointer to a variable that receives the actual size, in bytes, of the buffer allocated for this request.


### -param CacheEnabled [in]

Specifies whether the allocated memory can be cached.


## -returns



<b>VideoPortGetCommonBuffer</b> returns the base virtual address of the allocated buffer if successful; otherwise, returns <b>NULL</b> if the buffer cannot be allocated.




## -remarks



See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570178">VideoPortAllocateCommonBuffer</a>
 

 

