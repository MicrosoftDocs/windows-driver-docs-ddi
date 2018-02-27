---
UID: NF:video.VideoPortReleaseCommonBuffer
title: VideoPortReleaseCommonBuffer function
author: windows-driver-content
description: The VideoPortReleaseCommonBuffer function frees a common buffer that was previously allocated by VideoPortAllocateCommonBuffer.
old-location: display\videoportreleasecommonbuffer.htm
old-project: display
ms.assetid: b3733de1-63ef-43b8-b669-dbe7e573b499
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VideoPortReleaseCommonBuffer, VideoPortReleaseCommonBuffer function [Display Devices], VideoPort_Functions_78edd589-bea5-43e3-8658-8c6c95a1f0f7.xml, display.videoportreleasecommonbuffer, video/VideoPortReleaseCommonBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h, Ntdef.h
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
-	VideoPortReleaseCommonBuffer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortReleaseCommonBuffer function


## -description


The <b>VideoPortReleaseCommonBuffer</b> function frees a common buffer that was previously allocated by <a href="..\video\nf-video-videoportallocatecommonbuffer.md">VideoPortAllocateCommonBuffer</a>.


## -syntax


````
VOID VideoPortReleaseCommonBuffer(
  _In_ PVOID            HwDeviceExtension,
  _In_ PVP_DMA_ADAPTER  VpDmaAdapter,
  _In_ ULONG            Length,
  _In_ PHYSICAL_ADDRESS LogicalAddress,
  _In_ PVOID            VirtualAddress,
  _In_ BOOLEAN          CacheEnabled
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VpDmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter. This is the structure returned after a call to <a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>.


### -param Length [in]

Specifies the number of bytes of memory to be freed.


### -param LogicalAddress [in]

Specifies the logical address of the buffer to be freed.


### -param VirtualAddress [in]

Pointer to the corresponding virtual address of the allocated memory range. This value was obtained in a prior call to <a href="..\video\nf-video-videoportallocatecommonbuffer.md">VideoPortAllocateCommonBuffer</a>.


### -param CacheEnabled [in]

Indicates whether the allocated memory is cached. A value of <b>TRUE</b> indicates that the allocated memory is cached.


## -returns



None




## -remarks



The parameters passed to <b>VideoPortFreeCommonBuffer</b> must match exactly those passed to and returned from <b>VideoPortAllocateCommonBuffer</b>. A driver cannot free only part of an allocated common buffer. 




## -see-also

<a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>



<a href="..\video\nf-video-videoportallocatecommonbuffer.md">VideoPortAllocateCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortReleaseCommonBuffer function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

