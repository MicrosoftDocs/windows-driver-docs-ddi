---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT
title: IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT
author: windows-driver-content
description: The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the OUT direction.
old-location: buses\ioctl_internal_usbfn_control_status_handshake_out.htm
old-project: usbref
ms.assetid: C2CF94F3-E12D-4D31-975B-720FA5AB5ABA
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT, IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT control code [Buses], buses.ioctl_internal_usbfn_control_status_handshake_out, usbfnioctl/IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT
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
-	IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT
product: Windows
targetos: Windows
req.typenames: USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT IOCTL


## -description


The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the OUT direction. 


## -ioctlparameters




### -input-buffer

A <b>USBFNPIPEID</b> type value that indicates the pipe ID. The pipe ID of the default control endpoint is 0.


### -input-buffer-length

The size of a <b>USBFNPIPEID</b> type.


### -output-buffer

NULL.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks



This request must be sent after sending the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187891">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="https://msdn.microsoft.com/library/windows/hardware/mt187965">UfxEndpointCreate</a>.



