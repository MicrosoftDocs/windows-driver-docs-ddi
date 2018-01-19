---
UID: NI:nfcsedev.IOCTL_NFCSE_GET_NEXT_EVENT
title: IOCTL_NFCSE_GET_NEXT_EVENT
author: windows-driver-content
description: The IOCTL_NFCSE_GET_NEXT_EVENT control code returns the next event available in the buffer, or if there are no more buffered events remains pending until a secure element event is available. The event details must then be returned to the caller.
old-location: nfpdrivers\ioctl_nfcse_get_next_event.htm
old-project: nfpdrivers
ms.assetid: B142BB21-D70E-4BA2-B2C1-60468FA8378E
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_NFCSE_GET_NEXT_EVENT
req.alt-loc: nfcsedev.h
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
req.typenames: *PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE
---

# IOCTL_NFCSE_GET_NEXT_EVENT IOCTL



## -description
The <b>IOCTL_NFCSE_GET_NEXT_EVENT</b> 
   control code returns the next event available in the buffer, or if there are no more buffered events remains pending until a secure element event is available. The event details must then be returned to the caller.  



## -ioctlparameters

### -input-buffer
None


### -input-buffer-length
None


### -output-buffer

                A <b>DWORD</b> indicating the size of the <a href="..\nfcsedev\ns-nfcsedev-_secure_element_event_info.md">SECURE_ELEMENT_EVENT_INFO</a> structure plus its payload, immediately followed by the <b>SECURE_ELEMENT_EVENT_INFO</b> structure itself. 


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

 


## -remarks
The following are requirements that the driver must adhere to.<ul>
<li>
This IOCTL must be called on a handle that has an <b>SEEvents</b> relative file name; otherwise, the driver returns STATUS_INVALID_DEVICE_STATE

</li>
<li>
This driver must support CancelIO for this pending IOCTL.

</li>
<li>
This driver must maintain a received queue of the received secure element events that match the subscription type.

</li>
<li>
The following conditions must be met when this IOCTL is received in the driver:

<ul>
<li>
If the received queue is empty, then the driver must pend the IOCTL for later completion.

</li>
<li>
If the received queue is non-empty, then the driver must de-queue one event, copy the message buffer to the IOCTL’s output buffer, and complete the IOCTL with <b>STATUS_SUCCESS</b> immediately.

</li>
</ul>
</li>
<li>
If the driver completes this IOCTL with STATUS_SUCCESS, the first DWORD [4 bytes] of the output buffer must contain the size of the SECURE_ELEMENT_EVENT_INFO structure plus its payload.

</li>
<li>
If a received secure element event info is too large to be copied into this IOCTL’s buffer, the driver must copy the required buffer size into the first 4 bytes of the output buffer, set the IOCTL’s information field to sizeof(DWORD), and complete the IOCTL with <b>STATUS_BUFFER_OVERFLOW</b>. The event must then be left in the received queue.

</li>
</ul>


This IOCTL must be called on a handle that has an <b>SEEvents</b> relative file name; otherwise, the driver returns STATUS_INVALID_DEVICE_STATE

This driver must support CancelIO for this pending IOCTL.

This driver must maintain a received queue of the received secure element events that match the subscription type.

The following conditions must be met when this IOCTL is received in the driver:

If the received queue is empty, then the driver must pend the IOCTL for later completion.

If the received queue is non-empty, then the driver must de-queue one event, copy the message buffer to the IOCTL’s output buffer, and complete the IOCTL with <b>STATUS_SUCCESS</b> immediately.

If the driver completes this IOCTL with STATUS_SUCCESS, the first DWORD [4 bytes] of the output buffer must contain the size of the SECURE_ELEMENT_EVENT_INFO structure plus its payload.

If a received secure element event info is too large to be copied into this IOCTL’s buffer, the driver must copy the required buffer size into the first 4 bytes of the output buffer, set the IOCTL’s information field to sizeof(DWORD), and complete the IOCTL with <b>STATUS_BUFFER_OVERFLOW</b>. The event must then be left in the received queue.</p>