---
UID: NF:video.VideoPortReleaseBuffer
title: VideoPortReleaseBuffer function
author: windows-driver-content
description: The VideoPortReleaseBuffer function is obsolete in Windows 2000 and later. In its place, video miniport drivers should instead use VideoPortFreePool. VideoPortReleaseBuffer deallocates a block of paged pool memory.
old-location: display\videoportreleasebuffer.htm
old-project: display
ms.assetid: 627f43e7-1561-4822-b2b6-a49b54550bf5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortReleaseBuffer, VideoPortReleaseBuffer function [Display Devices], VideoPort_Functions_908af223-2ee5-4e86-b5ab-47f7f3cc459b.xml, display.videoportreleasebuffer, video/VideoPortReleaseBuffer
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
-	VideoPortReleaseBuffer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortReleaseBuffer function


## -description


The <b>VideoPortReleaseBuffer</b> function is <b>obsolete</b> in Windows 2000 and later. In its place, video miniport drivers should instead use <a href="https://msdn.microsoft.com/library/windows/hardware/ff570301">VideoPortFreePool</a>. 

<b>VideoPortReleaseBuffer</b> deallocates a block of paged pool memory.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param Buffer [in]

Specifies the address of the block of pool memory being deallocated.


## -returns



None




## -remarks



This function releases memory allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570177">VideoPortAllocateBuffer</a>. A miniport driver must not access the memory block to which <i>Buffer</i> points after it has been freed. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570177">VideoPortAllocateBuffer</a>
 

 

