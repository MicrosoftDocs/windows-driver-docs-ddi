---
UID: NC:usbcamdi.PCAM_START_CAPTURE_ROUTINE_EX
title: PCAM_START_CAPTURE_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamStartCaptureEx callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camstartcaptureex.htm
old-project: stream
ms.assetid: ab2222ed-3166-4984-b76c-5499879f91d5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _USB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
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
req.alt-api: CamStartCaptureEx
req.alt-loc: usbcamdi.h
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
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_START_CAPTURE_ROUTINE_EX callback



## -description
A camera minidriver's <b>CamStartCaptureEx</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.



## -prototype

````
PCAM_START_CAPTURE_ROUTINE_EX CamStartCaptureEx;

NTSTATUS CamStartCaptureEx(
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
<b>CamStartCaptureEx</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.


## -remarks
The original USBCAMD does not call <b>CamStartCaptureEx</b>.

This function is required.</p>