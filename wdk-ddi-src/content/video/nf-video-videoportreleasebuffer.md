---
UID: NF:video.VideoPortReleaseBuffer
title: VideoPortReleaseBuffer function
author: windows-driver-content
description: The VideoPortReleaseBuffer function is obsolete in Windows 2000 and later. In its place, video miniport drivers should instead use VideoPortFreePool. VideoPortReleaseBuffer deallocates a block of paged pool memory.
old-location: display\videoportreleasebuffer.htm
old-project: display
ms.assetid: 627f43e7-1561-4822-b2b6-a49b54550bf5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortReleaseBuffer, video/VideoPortReleaseBuffer, display.videoportreleasebuffer, VideoPort_Functions_908af223-2ee5-4e86-b5ab-47f7f3cc459b.xml, VideoPortReleaseBuffer function [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortReleaseBuffer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
---

# VideoPortReleaseBuffer function


## -description


The <b>VideoPortReleaseBuffer</b> function is <b>obsolete</b> in Windows 2000 and later. In its place, video miniport drivers should instead use <a href="..\video\nf-video-videoportfreepool.md">VideoPortFreePool</a>. 

<b>VideoPortReleaseBuffer</b> deallocates a block of paged pool memory.


## -syntax


````
VOID VideoPortReleaseBuffer(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID Buffer
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param Buffer [in]

Specifies the address of the block of pool memory being deallocated.


## -returns


None



## -remarks


This function releases memory allocated by <a href="..\video\nf-video-videoportallocatebuffer.md">VideoPortAllocateBuffer</a>. A miniport driver must not access the memory block to which <i>Buffer</i> points after it has been freed. 



## -see-also

<a href="..\video\nf-video-videoportallocatebuffer.md">VideoPortAllocateBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortReleaseBuffer function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

