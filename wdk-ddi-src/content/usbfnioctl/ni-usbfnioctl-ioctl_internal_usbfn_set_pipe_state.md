---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
title: IOCTL_INTERNAL_USBFN_SET_PIPE_STATE (usbfnioctl.h)
description: The class driver sends this request to set the stall state of the specified USB pipe.
old-location: buses\ioctl_internal_usbfn_set_pipe_state.htm
tech.root: usbref
ms.assetid: EB44DE6F-6B88-4F6D-B9AC-3FF7A519C047
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USBFN_SET_PIPE_STATE IOCTL"]
ms.keywords: IOCTL_INTERNAL_USBFN_SET_PIPE_STATE, IOCTL_INTERNAL_USBFN_SET_PIPE_STATE control, IOCTL_INTERNAL_USBFN_SET_PIPE_STATE control code [Buses], buses.ioctl_internal_usbfn_set_pipe_state, usbfnioctl/IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
f1_keywords:
 - "usbfnioctl/IOCTL_INTERNAL_USBFN_SET_PIPE_STATE"
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
- IOCTL_INTERNAL_USBFN_SET_PIPE_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USBFN_SET_PIPE_STATE IOCTL


## -description


The class driver sends this request to set the stall state of the specified USB pipe. 


## -ioctlparameters




### -input-buffer

A pointer to a <b>USBFNPIPEID</b> type that specifies the pipe ID.


### -input-buffer-length

The size of a <b>USBFNPIPEID</b> type.


### -output-buffer

A pointer to <b>BOOLEAN</b> value that  specifies the stall state to set. If TRUE,  USB Function Class Extension (UFX) sets the  pipe to stall state; FALSE sets to clear state.



### -output-buffer-length

The size of a <b>BOOLEAN</b>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

UFX completes the request with <b>STATUS_SUCCESS</b>.


## -remarks



This request must be sent after sending the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxendpointcreate">UfxEndpointCreate</a>.



