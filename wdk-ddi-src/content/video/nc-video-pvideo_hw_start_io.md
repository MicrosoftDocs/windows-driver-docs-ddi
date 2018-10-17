---
UID: NC:video.PVIDEO_HW_START_IO
title: PVIDEO_HW_START_IO
author: windows-driver-content
description: HwVidStartIO processes the specified VRP.
old-location: display\hwvidstartio.htm
tech.root: display
ms.assetid: 82951291-cf3e-486b-ad0e-f347fefe0370
ms.date: 5/10/2018
ms.keywords: HwVidStartIO, HwVidStartIO callback function [Display Devices], PVIDEO_HW_START_IO, PVIDEO_HW_START_IO callback, VideoMiniport_Functions_5dd4317e-f80d-4f93-86b5-b7c83aca2546.xml, display.hwvidstartio, video/HwVidStartIO
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidStartIO
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_HW_START_IO callback function


## -description


<i>HwVidStartIO</i> processes the specified <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VRP</a>.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param RequestPacket

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570547">VIDEO_REQUEST_PACKET</a> structure, which contains all the parameters originally passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564838">EngDeviceIoControl</a>.


## -returns



<i>HwVidStartIO</i> must return <b>TRUE</b>, indicating that it has completed the request.




## -remarks



Every video miniport driver must have a <i>HwVidStartIO</i> function.

The video port driver calls <i>HwVidStartIO</i> in response to each GDI <a href="https://msdn.microsoft.com/library/windows/hardware/ff564838">EngDeviceIoControl</a> request, which originates in the corresponding display driver. When <i>HwVidStartIO</i> is called, the miniport driver owns the input video request packet until it completes the requested operation. <i>HwVidStartIO</i> must do the following:

<ol>
<li>
Look at the <b>IoControlCode</b> member of the <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VRP</a> to determine the operation being requested by the display driver.

</li>
<li>
Check that the VRP <b>InputBufferLength</b> and/or <b>OutputBufferLength</b> indicates a buffer that is large enough to satisfy the request. The miniport driver should return an error if either buffer is too small.

</li>
<li>
Satisfy the request.

</li>
<li>
Set the <b>Status</b> and <b>Information</b> members in the <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VRP</a> and return <b>TRUE</b>.

</li>
</ol>
The system video port driver serializes all requests. A miniport driver need not perform any serialization of its own unless it has a <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> function.

However, every miniport driver's <i>HwVidStartIO</i> function must complete each requested operation or set an appropriate error in the VRP's <b>StatusBlock</b> before it returns control.

<i>HwVidStartIO</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570547">VIDEO_REQUEST_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570515">Video Miniport Driver I/O Control Codes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>
 

 

