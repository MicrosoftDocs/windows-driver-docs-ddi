---
UID: NF:video.VideoPortAllocateCommonBuffer
title: VideoPortAllocateCommonBuffer function
author: windows-driver-content
description: The VideoPortAllocateCommonBuffer function allocates and maps system memory so that it is simultaneously accessible from both the processor and a device for common-buffer DMA operations.
old-location: display\videoportallocatecommonbuffer.htm
old-project: display
ms.assetid: 950c2509-688e-4aaa-a12d-4106bb722bbc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoportallocatecommonbuffer, VideoPortAllocateCommonBuffer function [Display Devices], VideoPort_Functions_bd747ea0-7963-4008-a91c-eb5598fc6bdd.xml, VideoPortAllocateCommonBuffer, video/VideoPortAllocateCommonBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
-	VideoPortAllocateCommonBuffer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortAllocateCommonBuffer function


## -description


The <b>VideoPortAllocateCommonBuffer</b> function allocates and maps system memory so that it is simultaneously accessible from both the processor and a device for common-buffer DMA operations.


## -syntax


````
PVOID VideoPortAllocateCommonBuffer(
  _In_  PVOID             HwDeviceExtension,
  _In_  PVP_DMA_ADAPTER   VpDmaAdapter,
  _In_  ULONG             DesiredLength,
  _Out_ PPHYSICAL_ADDRESS LogicalAddress,
  _In_  BOOLEAN           CacheEnabled,
  _Out_ PVOID             Reserved
);
````


## -parameters




#### - HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


#### - VpDmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This structure was returned by a previous call to <a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>.


#### - DesiredLength [in]

Specifies the requested number of bytes of memory.


#### - LogicalAddress [out]

Pointer to a memory location that receives the logical address to be used by the adapter to access the allocated buffer.


#### - CacheEnabled [in]

Specifies whether the allocated memory can be cached.  For more information, see the description of the <i>CacheEnabled</i> parameter for <a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>.


#### - Reserved [out]

Is currently ignored by the video port driver; should be set to <b>NULL</b>.


## -returns


<b>VideoPortAllocateCommonBuffer</b> returns the base virtual address of the allocated buffer if successful; otherwise, it returns <b>NULL</b> if the buffer cannot be allocated.



## -remarks


When the buffer is no longer needed, the video miniport driver should release it by calling <a href="..\video\nf-video-videoportreleasecommonbuffer.md">VideoPortReleaseCommonBuffer</a>.



## -see-also

<a href="..\video\nf-video-videoportreleasecommonbuffer.md">VideoPortReleaseCommonBuffer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>

<a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>

<a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortAllocateCommonBuffer function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

