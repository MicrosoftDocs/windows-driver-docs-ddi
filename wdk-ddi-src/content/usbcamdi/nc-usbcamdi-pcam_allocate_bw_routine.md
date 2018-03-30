---
UID: NC:usbcamdi.PCAM_ALLOCATE_BW_ROUTINE
title: PCAM_ALLOCATE_BW_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamAllocateBandwidth callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camallocatebandwidth.htm
old-project: stream
ms.assetid: 0dd01bf7-04a8-4d20-982a-1ec81076583f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamAllocateBandwidth, CamAllocateBandwidth callback function [Streaming Media Devices], PCAM_ALLOCATE_BW_ROUTINE, stream.camallocatebandwidth, usbcamdi/CamAllocateBandwidth, usbcmdpr_4e7b22dc-0f6d-4a9b-82df-61c14cae981b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
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
-	usbcamdi.h
api_name:
-	CamAllocateBandwidth
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_ALLOCATE_BW_ROUTINE callback


## -description


<p class="CCE_Message">[CamAllocateBandwidth is not supported and may be altered or unavailable in the future. Instead, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff557600">CamAllocateBandwidthEx</a>.
]

A camera minidriver's <b>CamAllocateBandwidth</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param RawFrameLength

Specifies the size, of the raw frame data from the packet stream, in bytes.


### -param Format

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567331">KS_DATAFORMAT_VIDEOINFOHEADER</a> structure that is associated with this stream.


## -returns



<b>CamAllocateBandwidth</b> returns STATUS_SUCCESS or an appropriate error code.




## -remarks



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568585">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamAllocateBandwidth</b> callback function immediately before the isochronous video capture stream is started. It is called in connection with a <b>Run</b> command.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

This function is required.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557600">CamAllocateBandwidthEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567331">KS_DATAFORMAT_VIDEOINFOHEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568625">USBCAMD_SelectAlternateInterface</a>
 

 

