---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_TRANSFER_IN
title: IOCTL_INTERNAL_USBFN_TRANSFER_IN (usbfnioctl.h)
description: The class driver sends this request to initiate a data transfer to the host on the specified pipe.
old-location: buses\_ioctl_internal_usbfn_transfer_in.htm
tech.root: usbref
ms.assetid: 53F895F8-596D-464C-866E-67028CF644E4
ms.date: 05/07/2018
ms.keywords: IOCTL_INTERNAL_USBFN_TRANSFER_IN, IOCTL_INTERNAL_USBFN_TRANSFER_IN control, IOCTL_INTERNAL_USBFN_TRANSFER_IN control code [Buses], buses._ioctl_internal_usbfn_transfer_in, usbfnioctl/IOCTL_INTERNAL_USBFN_TRANSFER_IN
ms.topic: ioctl
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
- IOCTL_INTERNAL_USBFN_TRANSFER_IN
product:
- Windows
targetos: Windows
req.typenames: 
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








### -inout-buffer-length








### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks



This request must be sent after sending the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.



