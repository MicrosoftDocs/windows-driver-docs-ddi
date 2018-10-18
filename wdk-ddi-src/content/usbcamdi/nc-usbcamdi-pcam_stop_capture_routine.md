---
UID: NC:usbcamdi.PCAM_STOP_CAPTURE_ROUTINE
title: PCAM_STOP_CAPTURE_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamStopCapture callback function performs any processing after the stream is stopped.
old-location: stream\camstopcapture.htm
tech.root: stream
ms.assetid: c4403edb-3035-469b-bdb9-c33882a1c90c
ms.date: 4/23/2018
ms.keywords: CamStopCapture, CamStopCapture callback function [Streaming Media Devices], PCAM_STOP_CAPTURE_ROUTINE, PCAM_STOP_CAPTURE_ROUTINE callback, stream.camstopcapture, usbcamdi/CamStopCapture, usbcmdpr_56cc6085-dfff-4576-b19a-45683a7b62d8.xml
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
-	CamStopCapture
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCAM_STOP_CAPTURE_ROUTINE callback function


## -description


<p class="CCE_Message">[CamStopCapture is not supported and may be altered or unavailable in the future. Instead, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff557643">CamStopCaptureEx</a>.
]

A camera minidriver's <b>CamStopCapture</b> callback function performs any processing after the stream is stopped.


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


## -returns



<b>CamStopCapture</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.




## -remarks



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568585">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the minidriver's <b>CamStopCapture</b> callback function immediately after the isochronous video stream is stopped. Typically, a camera minidriver selects an alternate setting within the USB video streaming interface that uses no additional bandwidth.

This function is required.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557643">CamStopCaptureEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568590">USBCAMD_DEVICE_DATA2</a>
 

 

