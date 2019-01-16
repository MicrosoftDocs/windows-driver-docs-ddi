---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_GET_PIPE_STATE
title: IOCTL_INTERNAL_USBFN_GET_PIPE_STATE
description: The class driver sends this request to get the stall state of the specified pipe.
old-location: buses\ioctl_internal_usbfn_get_pipe_state.htm
tech.root: usbref
ms.assetid: CFBFC5E4-852C-4287-A85E-2EF3C89FE474
ms.date: 05/07/2018
ms.keywords: IOCTL_INTERNAL_USBFN_GET_PIPE_STATE, IOCTL_INTERNAL_USBFN_GET_PIPE_STATE control, IOCTL_INTERNAL_USBFN_GET_PIPE_STATE control code [Buses], buses.ioctl_internal_usbfn_get_pipe_state, usbfnioctl/IOCTL_INTERNAL_USBFN_GET_PIPE_STATE
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnioctl.h
api_name:
-	IOCTL_INTERNAL_USBFN_GET_PIPE_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USBFN_GET_PIPE_STATE IOCTL


## -description


The class driver sends this request to get the stall state of the specified pipe.


## -ioctlparameters




### -input-buffer

A pointer to a <b>USBFNPIPEID</b> type that specifies the pipe ID.


### -input-buffer-length

The size of a <b>USBFNPIPEID</b> type.


### -output-buffer

A pointer to <b>BOOLEAN</b> value that  is set by USB Function Class Extension (UFX) to indicate whether or not the specified pipe is stalled. TRUE, indicates the pipe is in stall state; FALSE indicates the pipe is in clear state.



### -output-buffer-length

The size of a <b>BOOLEAN</b>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

UFX completes the request with <b>STATUS_SUCCESS</b>.


## -remarks



This request must be sent after sending the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187891">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

When stalled, the pipe sends STALL transaction packets to the host. See the Universal Serial Bus (USB) specification for more information.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.



