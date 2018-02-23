---
UID: NF:video.VideoPortGetCommonBuffer
title: VideoPortGetCommonBuffer function
author: windows-driver-content
description: The VideoPortGetCommonBuffer function is obsolete in Windows XP and later, and is supported only for backward compatibility with existing drivers.
old-location: display\videoportgetcommonbuffer.htm
old-project: display
ms.assetid: c8329d26-fb6f-46f1-aacd-ba78ee4ea5d5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: VideoPortGetCommonBuffer, VideoPort_Functions_eead14aa-271b-49a2-8ded-482ffc73741e.xml, VideoPortGetCommonBuffer function [Display Devices], display.videoportgetcommonbuffer, video/VideoPortGetCommonBuffer
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
-	VideoPortGetCommonBuffer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetCommonBuffer function


## -description


The <b>VideoPortGetCommonBuffer</b> function is <b>obsolete</b> in Windows XP and later, and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="..\video\nf-video-videoportallocatecommonbuffer.md">VideoPortAllocateCommonBuffer</a>.

<b>VideoPortGetCommonBuffer</b> allocates and maps system memory so that it is simultaneously accessible from both the processor and a device for common-buffer DMA operations.


## -syntax


````
PVOID VideoPortGetCommonBuffer(
  _In_  PVOID             HwDeviceExtension,
  _In_  ULONG             DesiredLength,
  _In_  ULONG             Alignment,
  _Out_ PPHYSICAL_ADDRESS LogicalAddress,
  _Out_ PULONG            pActualLength,
  _In_  BOOLEAN           CacheEnabled
);
````


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

<a href="..\video\nf-video-videoportallocatecommonbuffer.md">VideoPortAllocateCommonBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortGetCommonBuffer function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

