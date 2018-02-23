---
UID: NC:usbcamdi.PCAM_STOP_CAPTURE_ROUTINE
title: PCAM_STOP_CAPTURE_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamStopCapture callback function performs any processing after the stream is stopped.
old-location: stream\camstopcapture.htm
old-project: stream
ms.assetid: c4403edb-3035-469b-bdb9-c33882a1c90c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: stream.camstopcapture, CamStopCapture, CamStopCapture callback function [Streaming Media Devices], CamStopCapture, PCAM_STOP_CAPTURE_ROUTINE, PCAM_STOP_CAPTURE_ROUTINE, usbcamdi/CamStopCapture, usbcmdpr_56cc6085-dfff-4576-b19a-45683a7b62d8.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbcamdi.h
apiname:
-	CamStopCapture
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_STOP_CAPTURE_ROUTINE callback


## -description


<p class="CCE_Message">[CamStopCapture is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine_ex.md">CamStopCaptureEx</a>.
]

A camera minidriver's <b>CamStopCapture</b> callback function performs any processing after the stream is stopped.


## -prototype


````
NTSTATUS CamStopCapture(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext
);
````


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


## -returns



<b>CamStopCapture</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.




## -remarks



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the minidriver's <b>CamStopCapture</b> callback function immediately after the isochronous video stream is stopped. Typically, a camera minidriver selects an alternate setting within the USB video streaming interface that uses no additional bandwidth.

This function is required.




## -see-also

<a href="..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine_ex.md">CamStopCaptureEx</a>



<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_STOP_CAPTURE_ROUTINE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

