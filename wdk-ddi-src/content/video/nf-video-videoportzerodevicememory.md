---
UID: NF:video.VideoPortZeroDeviceMemory
title: VideoPortZeroDeviceMemory function
author: windows-driver-content
description: The VideoPortZeroDeviceMemory function fills an adapter frame buffer or other device memory with zeros.
old-location: display\videoportzerodevicememory.htm
old-project: display
ms.assetid: 1f59ae13-022b-426c-9eef-9a8e5f5a85f2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortZeroDeviceMemory, VideoPortZeroDeviceMemory function [Display Devices], display.videoportzerodevicememory, VideoPort_Functions_42829075-dd6d-49fd-a4d6-3ee19152335d.xml, video/VideoPortZeroDeviceMemory
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortZeroDeviceMemory
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortZeroDeviceMemory function


## -description


The <b>VideoPortZeroDeviceMemory</b> function fills an adapter <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a> or other device memory with zeros.


## -syntax


````
VOID VideoPortZeroDeviceMemory(
  _Out_ PVOID Destination,
        ULONG Length
);
````


## -parameters




### -param Destination [out]

Specifies the base address of the adapter memory area. This value must be a mapped logical address returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.


### -param Length

Specifies the size, in bytes, to be filled.


## -returns


None



## -remarks


Miniport drivers should <i>always</i> call this function, rather than <b>VideoPortZeroMemory</b>, to fill on-adapter memory with zeros.

A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortZeroDeviceMemory</b>.

Callers of <b>VideoPortZeroDeviceMemory</b> can be running at any IRQL if the memory pointed to by the <i>Destination</i> parameter is in nonpaged pool. Otherwise, the caller must be running at IRQL &lt; DISPATCH_LEVEL.



## -see-also

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>

<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>

<a href="..\video\nf-video-videoportzeromemory.md">VideoPortZeroMemory</a>

<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortZeroDeviceMemory function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

