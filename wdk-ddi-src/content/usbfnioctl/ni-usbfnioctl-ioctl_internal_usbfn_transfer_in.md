---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_TRANSFER_IN
title: IOCTL_INTERNAL_USBFN_TRANSFER_IN
author: windows-driver-content
description: The class driver sends this request to initiate a data transfer to the host on the specified pipe.
old-location: buses\_ioctl_internal_usbfn_transfer_in.htm
old-project: usbref
ms.assetid: 53F895F8-596D-464C-866E-67028CF644E4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USBFN_USB_STRING, *PUSBFN_USB_STRING, USBFN_USB_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbfnioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_USBFN_TRANSFER_IN
req.alt-loc: usbfnioctl.h
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
req.typenames: *PUSBFN_USB_STRING, USBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_TRANSFER_IN IOCTL



## -description
The class driver sends this request to initiate a data transfer to the host on the specified pipe. 



## -ioctlparameters

### -input-buffer
A pointer to a <b>USBFNPIPEID</b> type that specifies the pipe ID.


### -input-buffer-length
The size of a <b>USBFNPIPEID</b> type.


### -output-buffer
The  output buffer points to a buffer containing the data to be sent. The IN direction is from the host perspective representing an outbound transfer from the device to the host.


### -output-buffer-length
The length of the data to be sent.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks
This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.</p>