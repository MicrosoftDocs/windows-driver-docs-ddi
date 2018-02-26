---
UID: NC:usbcamdi.PCAM_STOP_CAPTURE_ROUTINE_EX
title: PCAM_STOP_CAPTURE_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamStopCaptureEx callback function performs any processing after the stream is stopped.
old-location: stream\camstopcaptureex.htm
old-project: stream
ms.assetid: b8b6e3f0-f5c8-449f-9001-3182b3547d8d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamStopCaptureEx, CamStopCaptureEx routine [Streaming Media Devices], PCAM_STOP_CAPTURE_ROUTINE_EX, stream.camstopcaptureex, usbcamdi/CamStopCaptureEx, usbcmdpr_ce30ba35-3109-454c-bef4-30ff5d6805de.xml
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
-	CamStopCaptureEx
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_STOP_CAPTURE_ROUTINE_EX callback


## -description


A camera minidriver's <b>CamStopCaptureEx</b> callback function performs any processing after the stream is stopped.


## -prototype


````
PCAM_STOP_CAPTURE_ROUTINE_EX CamStopCaptureEx;

NTSTATUS CamStopCaptureEx(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext,
   ULONG          StreamNumber
)
{ ... }
````


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param StreamNumber

Indicates the stream number.


## -returns



<b>CamStopCaptureEx</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.




## -remarks



USBCAMD calls the minidriver's <b>CamStopCaptureEx</b> callback function immediately after the isochronous video stream is stopped. Typically, a camera minidriver selects an alternate setting within the USB video streaming interface that uses no additional bandwidth.

The original USBCAMD does not call <b>CamStopCaptureEx</b>.

This function is required.



