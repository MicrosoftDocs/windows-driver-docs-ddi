---
UID: NC:usbcamdi.PCAM_INITIALIZE_ROUTINE
title: PCAM_INITIALIZE_ROUTINE
author: windows-driver-content
description: A camera minidriver's callback function initializes the device or performs any minidriver-specific clean-up that is required.
old-location: stream\caminitialize.htm
old-project: stream
ms.assetid: a39f78b7-f749-40b8-952a-5442608b0f1f
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
req.alt-api: MyInitialize
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

# PCAM_INITIALIZE_ROUTINE callback



## -description
A camera minidriver's callback function initializes the device or  performs any minidriver-specific clean-up that is required. 



## -prototype

````
PCAM_INITIALIZE_ROUTINE MyInitialize;

NTSTATUS MyInitialize(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext
)
{ ... }
````


## -parameters

### -param BusDeviceObject 

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext 

Pointer to the camera minidriver's device context.


## -returns
<b>CamInitialize</b> returns STATUS_SUCCESS or an appropriate error code. 


## -remarks
<b>About CamInitialize</b>

USBCAMD calls the camera minidriver's <b>CamInitialize</b> callback function the first time the device is used.

<b>CamInitialize</b> is called by both the original USBCAMD and USBCAMD2.

This function is required.

<b>About CamUnInitialize</b>

USBCAMD calls the camera minidriver's <b>CamUnInitialize</b> callback function while processing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568215">SRB_UNINITIALIZE_DEVICE</a> request. The <b>CamUnInitialize</b> function in version 1.0 is invoked after the user no longer requires the peripheral for that session.

Whereas the stream class driver automatically resets values associated with the minidriver, this call allows the minidriver to deallocate any specific resources used during its operation, such as memory used to store processed and decoded video frames.

<b>CamUnInitialize</b> is called by both versions 1.0 and 2.0 of USBCAMD.</p>