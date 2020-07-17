---
UID: NC:usbcamdi.PCAM_START_CAPTURE_ROUTINE
title: PCAM_START_CAPTURE_ROUTINE (usbcamdi.h)
description: A camera minidriver's CamStartCapture callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camstartcapture.htm
tech.root: stream
ms.assetid: e929f8c1-fe36-4374-976f-b0bfb3e0b4a2
ms.date: 04/23/2018
keywords: ["PCAM_START_CAPTURE_ROUTINE callback function"]
ms.keywords: CamStartCapture, CamStartCapture callback function [Streaming Media Devices], PCAM_START_CAPTURE_ROUTINE, PCAM_START_CAPTURE_ROUTINE callback, stream.camstartcapture, usbcamdi/CamStartCapture, usbcmdpr_c4887b29-94a3-498f-ad6a-4f6a58bb8345.xml
f1_keywords:
 - "usbcamdi/CamStartCapture"
 - "CamStartCapture"
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
- CamStartCapture
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCAM_START_CAPTURE_ROUTINE callback function


## -description


<p class="CCE_Message">[CamStartCapture is not supported and may be altered or unavailable in the future. Instead, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_start_capture_routine_ex">CamStartCaptureEx</a>.
]

A camera minidriver's <b>CamStartCapture</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.


## -parameters




### -param BusDeviceObject

Pointer to camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to camera minidriver's device context.


## -returns



<b>CamStartCapture</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.




## -remarks



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamStartCapture</b> callback function immediately prior to the start of the isochronous video capture stream. <b>CamStartCapture</b> is called in the context of a <b>Run</b> command.

This function is required.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_start_capture_routine_ex">CamStartCaptureEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data">USBCAMD_DEVICE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data2">USBCAMD_DEVICE_DATA2</a>
 

 

