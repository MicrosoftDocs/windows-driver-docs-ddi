---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
title: IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN (usbfnioctl.h)
description: The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the IN direction.
old-location: buses\_ioctl_internal_usbfn_control_status_handshake_in.htm
tech.root: usbref
ms.assetid: 5839C1A8-6638-4A42-B7C1-168071C99800
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN, IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN control, IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN control code [Buses], buses._ioctl_internal_usbfn_control_status_handshake_in, usbfnioctl/IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
 - usbfnioctl/IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnioctl.h
api_name:
 - IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
---

# IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN IOCTL


## -description

The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the IN direction.

## -ioctlparameters

### -input-buffer

A <b>USBFNPIPEID</b> type value that indicates the pipe ID. The pipe ID of the default control endpoint is 0.

### -input-buffer-length

The size of a <b>USBFNPIPEID</b> type.

### -output-buffer

NULL.

### -output-buffer-length

NULL.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

This request must be sent after sending the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.

