---
UID: NF:video.VideoPortZeroMemory
title: VideoPortZeroMemory function
author: windows-driver-content
description: The VideoPortZeroMemory function fills a block of system memory with zeros.
old-location: display\videoportzeromemory.htm
old-project: display
ms.assetid: 96827d2e-0fee-4276-a758-82f5b7383eec
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortZeroMemory
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
req.alt-api: VideoPortZeroMemory
req.alt-loc: Videoprt.sys
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
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortZeroMemory function



## -description
The <b>VideoPortZeroMemory</b> function fills a block of system memory with zeros.



## -syntax

````
VOID VideoPortZeroMemory(
  _Out_ PVOID Destination,
        ULONG Length
);
````


## -parameters

### -param Destination [out]

Specifies the starting address of the block of memory. This value must be in a mapped logical range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.


### -param Length 

Specifies the size, in bytes, of the block.


## -returns
None


## -remarks
Miniport drivers' <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> functions generally call <b>VideoPortZeroMemory</b> to initialize the <a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a> structure with zeros.

The given <i>Destination</i> must be in a mapped logical range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a> and/or a <a href="wdkgloss.s#wdkgloss.system_space#wdkgloss.system_space"><i>system space</i></a> RAM address, such as an address on the stack. Use <a href="..\video\nf-video-videoportzerodevicememory.md">VideoPortZeroDeviceMemory</a> to fill any device-memory block, such as a <a href="wdkgloss.f#wdkgloss.frame_buffer#wdkgloss.frame_buffer"><i>frame buffer</i></a>, with zeros.

A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortZeroMemory</b>.

Callers of <b>VideoPortZeroMemory</b> can be running at any IRQL if the memory pointed to by the <i>Destination</i> parameter is in nonpaged pool. Otherwise, the caller must be running at IRQL &lt; DISPATCH_LEVEL.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>
</dt>
<dt>
<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>
</dt>
<dt>
<a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportcomparememory.md">VideoPortCompareMemory</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportmovememory.md">VideoPortMoveMemory</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportzerodevicememory.md">VideoPortZeroDeviceMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortZeroMemory function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

