---
UID: NF:video.VideoPortPutDmaAdapter
title: VideoPortPutDmaAdapter function
author: windows-driver-content
description: The VideoPortPutDmaAdapter function frees a VP_DMA_ADAPTER structure that was previously allocated by a call to VideoPortGetDmaAdapter.
old-location: display\videoportputdmaadapter.htm
old-project: display
ms.assetid: 80f1f1bd-57da-46b2-9967-9ba4b08ea057
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: VideoPort_Functions_3de2fb91-53a9-4a1d-9dcd-91e3c0d645ab.xml, video/VideoPortPutDmaAdapter, VideoPortPutDmaAdapter, VideoPortPutDmaAdapter function [Display Devices], display.videoportputdmaadapter
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
-	VideoPortPutDmaAdapter
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortPutDmaAdapter function


## -description


The <b>VideoPortPutDmaAdapter</b> function frees a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that was previously allocated by a call to <a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>.


## -syntax


````
VOID VideoPortPutDmaAdapter(
  _In_ PVOID           HwDeviceExtension,
  _In_ PVP_DMA_ADAPTER VpDmaAdapter
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VpDmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a> structure that represents the bus-master adapter.


## -returns



None




## -remarks



A miniport driver should call this function only if it will not use the same VP_DMA_ADAPTER structure again.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570570">VP_DMA_ADAPTER</a>



<a href="..\video\nf-video-videoportgetdmaadapter.md">VideoPortGetDmaAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortPutDmaAdapter function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

