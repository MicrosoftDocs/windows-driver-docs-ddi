---
UID: NC:usbcamdi.PCAM_STOP_CAPTURE_ROUTINE
title: PCAM_STOP_CAPTURE_ROUTINE (usbcamdi.h)
description: A camera minidriver's CamStopCapture callback function performs any processing after the stream is stopped.
old-location: stream\camstopcapture.htm
tech.root: stream
ms.assetid: c4403edb-3035-469b-bdb9-c33882a1c90c
ms.date: 04/23/2018
keywords: ["PCAM_STOP_CAPTURE_ROUTINE callback function"]
ms.keywords: CamStopCapture, CamStopCapture callback function [Streaming Media Devices], PCAM_STOP_CAPTURE_ROUTINE, PCAM_STOP_CAPTURE_ROUTINE callback, stream.camstopcapture, usbcamdi/CamStopCapture, usbcmdpr_56cc6085-dfff-4576-b19a-45683a7b62d8.xml
f1_keywords:
 - "usbcamdi/CamStopCapture"
 - "CamStopCapture"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- usbcamdi.h
api_name:
- CamStopCapture
targetos: Windows
req.typenames: 
---

# PCAM_STOP_CAPTURE_ROUTINE callback function


## -description


<p class="CCE_Message">[CamStopCapture is not supported and may be altered or unavailable in the future. Instead, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_stop_capture_routine_ex">CamStopCaptureEx</a>.
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



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the minidriver's <b>CamStopCapture</b> callback function immediately after the isochronous video stream is stopped. Typically, a camera minidriver selects an alternate setting within the USB video streaming interface that uses no additional bandwidth.

This function is required.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_stop_capture_routine_ex">CamStopCaptureEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data2">USBCAMD_DEVICE_DATA2</a>
 

 

