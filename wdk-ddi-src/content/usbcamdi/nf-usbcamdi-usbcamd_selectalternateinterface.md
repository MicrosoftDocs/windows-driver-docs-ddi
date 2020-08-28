---
UID: NF:usbcamdi.USBCAMD_SelectAlternateInterface
title: USBCAMD_SelectAlternateInterface function (usbcamdi.h)
description: The USBCAMD_SelectAlternateInterface function selects an alternate setting within the USB video streaming interface.
old-location: stream\usbcamd_selectalternateinterface.htm
tech.root: stream
ms.assetid: b9a31719-2674-4d3f-8792-b099640faa07
ms.date: 04/23/2018
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

# USBCAMD_SelectAlternateInterface function


## -description

The <b>USBCAMD_SelectAlternateInterface</b> function selects an alternate setting within the USB video streaming interface.

## -parameters

### -param DeviceContext 

[in]
Pointer to a device-specific context.

### -param RequestInterface 

[in, out]
Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a> structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.

## -returns

<b>USBCAMD_SelectAlternateInterface </b>returns the status of the SELECT_INTERFACE USB bus driver request. Other possible error codes include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_DATA_ERROR</b></dt>
</dl>
</td>
<td width="60%">
USBCAMD failed to cancel outstanding bulk/interrupt IRPs.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to allocate the USB request block

</td>
</tr>
</table>

## -remarks

On successful completion, the structure pointed to by the <i>RequestInterface</i> argument is filled in with the information from the SELECT_INTERFACE USB bus driver request.

This function is typically called by a camera minidriver in response to a request to allocate or free bandwidth. This function should not be called when any video streams in the minidriver are open and/or actively streaming data.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a>

