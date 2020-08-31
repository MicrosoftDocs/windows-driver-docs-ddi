---
UID: NC:usbcamdi.PCAM_STOP_CAPTURE_ROUTINE_EX
title: PCAM_STOP_CAPTURE_ROUTINE_EX (usbcamdi.h)
description: A camera minidriver's CamStopCaptureEx callback function performs any processing after the stream is stopped.
old-location: stream\camstopcaptureex.htm
tech.root: stream
ms.assetid: b8b6e3f0-f5c8-449f-9001-3182b3547d8d
ms.date: 04/23/2018
keywords: ["PCAM_STOP_CAPTURE_ROUTINE_EX callback function"]
ms.keywords: CamStopCaptureEx, CamStopCaptureEx routine [Streaming Media Devices], PCAM_STOP_CAPTURE_ROUTINE_EX, stream.camstopcaptureex, usbcamdi/CamStopCaptureEx, usbcmdpr_ce30ba35-3109-454c-bef4-30ff5d6805de.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PCAM_STOP_CAPTURE_ROUTINE_EX
 - usbcamdi/PCAM_STOP_CAPTURE_ROUTINE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - CamStopCaptureEx
---

# PCAM_STOP_CAPTURE_ROUTINE_EX callback function


## -description

A camera minidriver's <b>CamStopCaptureEx</b> callback function performs any processing after the stream is stopped.

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

