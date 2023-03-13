---
UID: NF:usbcamdi.USBCAMD_SelectAlternateInterface
title: USBCAMD_SelectAlternateInterface function (usbcamdi.h)
description: The USBCAMD_SelectAlternateInterface function selects an alternate setting within the USB video streaming interface.
tech.root: stream
ms.date: 03/08/2023
keywords: ["USBCAMD_SelectAlternateInterface function"]
ms.keywords: USBCAMD_SelectAlternateInterface, USBCAMD_SelectAlternateInterface function [Streaming Media Devices], stream.usbcamd_selectalternateinterface, usbcamdi/USBCAMD_SelectAlternateInterface, usbcmdpr_48a3328b-869a-42fd-acfd-b1981384db85.xml
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - USBCAMD_SelectAlternateInterface
 - usbcamdi/USBCAMD_SelectAlternateInterface
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - usbcamd2.lib
 - usbcamd2.dll
api_name:
 - USBCAMD_SelectAlternateInterface
---

## -description

The **USBCAMD_SelectAlternateInterface** function selects an alternate setting within the USB video streaming interface.

## -parameters

### -param DeviceContext [in]

Pointer to a device-specific context.

### -param RequestInterface [in, out]

Pointer to a [USBD_INTERFACE_INFORMATION](/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information) structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.

## -returns

**USBCAMD_SelectAlternateInterface** returns the status of the SELECT_INTERFACE USB bus driver request. Other possible error codes include:

| Return code | Description |
|---|---|
| **STATUS_DEVICE_DATA_ERROR** | USBCAMD failed to cancel outstanding bulk/interrupt IRPs. |
| **STATUS_INSUFFICIENT_RESOURCES** | There are insufficient resources to allocate the USB request block |

## -remarks

On successful completion, the structure pointed to by the *RequestInterface* argument is filled in with the information from the SELECT_INTERFACE USB bus driver request.

This function is typically called by a camera minidriver in response to a request to allocate or free bandwidth. This function should not be called when any video streams in the minidriver are open and/or actively streaming data.

## -see-also

[USBD_INTERFACE_INFORMATION](/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information)
