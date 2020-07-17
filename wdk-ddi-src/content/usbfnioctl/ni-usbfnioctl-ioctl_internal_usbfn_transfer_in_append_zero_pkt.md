---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT
title: IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT (usbfnioctl.h)
description: The class driver sends this request to initiate an IN transfer to the specified pipe and appends a zero-length packet to indicate the end of the transfer.
old-location: buses\ioctl_internal_usbfn_transfer_in_append_zero_pkt.htm
tech.root: usbref
ms.assetid: 3912A632-E9D0-42D5-B7B7-766A92EE8C95
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT, IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT control, IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT control code [Buses], buses.ioctl_internal_usbfn_transfer_in_append_zero_pkt, usbfnioctl/IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT
f1_keywords:
 - "usbfnioctl/IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT"
 - "IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT"
req.header: usbfnioctl.h
req.include-header: 
req.target-type: Windows
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
- HeaderDef
api_location:
- usbfnioctl.h
api_name:
- IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT IOCTL


## -description


The class driver sends this request to initiate an IN transfer to the specified pipe and appends a zero-length packet to indicate the end of the transfer. 


## -ioctlparameters




### -input-buffer

A pointer to a <b>USBFNPIPEID</b> type that specifies the pipe ID.


### -input-buffer-length

The size of a <b>USBFNPIPEID</b> type.


### -output-buffer

The  output buffer points to a data buffer containing the data to be sent. The IN direction is from the host perspective representing an outbound transfer from the device to the host.


### -output-buffer-length

The size of the data to be sent.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks



This request must be sent after sending the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.

The function controller initiates a transfer in the IN direction on the endpoint and automatically appends a zero-length packet transfer after the data provided in the data buffer is successfully sent. A zero-length packet is only appended by the controller if the size of the transfer payload is a multiple of the endpoint’s maximum packet size.



