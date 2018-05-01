---
UID: NS:video._VIDEO_REQUEST_PACKET
title: "_VIDEO_REQUEST_PACKET"
author: windows-driver-content
description: A pointer to a VIDEO_REQUEST_PACKET structure is passed to the miniport driver's HwVidStartIO function by the video port driver.
old-location: display\video_request_packet.htm
old-project: display
ms.assetid: 8ccc8c97-4c8c-4278-8eef-a612ce85439e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PVIDEO_REQUEST_PACKET, PVIDEO_REQUEST_PACKET, PVIDEO_REQUEST_PACKET structure pointer [Display Devices], VIDEO_REQUEST_PACKET, VIDEO_REQUEST_PACKET structure [Display Devices], Video_Structs_38b404b6-a625-43a4-b2ad-21749c64eee1.xml, _VIDEO_REQUEST_PACKET, display.video_request_packet, video/PVIDEO_REQUEST_PACKET, video/VIDEO_REQUEST_PACKET"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_REQUEST_PACKET
product: Windows
targetos: Windows
req.typenames: VIDEO_REQUEST_PACKET, *PVIDEO_REQUEST_PACKET
---

# _VIDEO_REQUEST_PACKET structure


## -description


A pointer to a VIDEO_REQUEST_PACKET structure is passed to the miniport driver's <a href="https://msdn.microsoft.com/82951291-cf3e-486b-ad0e-f347fefe0370">HwVidStartIO</a> function by the video port driver. The video port driver sets up the <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VRP</a> from the IRP code (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550710">IRP Major Function Codes</a>) sent in response to a GDI call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564838">EngDeviceIoControl</a>. Usually, the corresponding display driver makes the call to <b>EngDeviceIoControl</b> when it needs support from the video port-miniport driver pair. The video port driver calls the miniport driver with the <i>VRP</i> to process the given IOCTL_VIDEO_<i>XXX</i> request.


## -struct-fields




### -field IoControlCode

Specifies an IOCTL_VIDEO_<i>XXX</i> value passed to the <b>EngDeviceIoControl</b> function by the caller and sent to the video port driver in an IRP code. For more information about the set of system-defined IOCTL_VIDEO_<i>XXX</i> that miniport drivers must support, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff570515">Video Miniport Driver I/O Control Codes</a>.


### -field StatusBlock

Pointer to a STATUS_BLOCK structure in the <a href="https://msdn.microsoft.com/a1de1905-09f3-4689-ace9-06690a1f930a">VRP</a>. <b>StatusBlock</b> is filled in by the miniport driver with return information upon completion of each VRP.


### -field InputBuffer

Pointer to an input buffer that contains information passed in by the caller. The structure for the data depends on the value of <b>IoControlCode</b>. This member actually points to the same buffer as that indicated by <b>OutputBuffer</b>.


### -field InputBufferLength

Specifies the size in bytes of the input buffer.


### -field OutputBuffer

Pointer to an output buffer into which the miniport driver transfers data to be returned to the caller. The structure for the data depends on the value of <b>IoControlCode.</b> Because this member points to the same buffer as <b>InputBuffer</b>, a miniport driver must not write output in the <b>OutputBuffer</b> before it has consumed all input data from the <b>InputBuffer</b>.


### -field OutputBufferLength

Specifies the size in bytes of the output buffer. A miniport driver cannot enlarge this buffer. A miniport driver should set the <b>Status</b> member of the <b>StatusBlock</b> with ERROR_INSUFFICIENT_BUFFER or ERROR_MORE_DATA if the given <b>OutputBuffer</b> is too small to contain all the returned information.


## -see-also




<a href="https://msdn.microsoft.com/82951291-cf3e-486b-ad0e-f347fefe0370">HwVidStartIO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570515">Video Miniport Driver I/O Control Codes</a>
 

 

