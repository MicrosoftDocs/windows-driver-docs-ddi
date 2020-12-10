---
UID: NF:udecxurb.UdecxUrbRetrieveBuffer
title: UdecxUrbRetrieveBuffer function (udecxurb.h)
description: Retrieves the transfer buffer of an URB from the specified framework request object sent to the endpoint queue.
old-location: buses\udecxurbretrievebuffer.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUrbRetrieveBuffer function"]
ms.keywords: UdecxUrbRetrieveBuffer, UdecxUrbRetrieveBuffer function [Buses], buses.udecxurbretrievebuffer, udecxurb/UdecxUrbRetrieveBuffer
req.header: udecxurb.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UdecxUrbRetrieveBuffer
 - udecxurb/UdecxUrbRetrieveBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUrbRetrieveBuffer
---

# UdecxUrbRetrieveBuffer function


## -description

Retrieves the transfer buffer of an URB from the specified framework request object sent to the endpoint queue.

## -parameters

### -param Request 

[in]
A handle to a framework request object that contains the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> for the transfer.

### -param TransferBuffer 

[out]
A pointer to a buffer that receives the transfer buffer of an <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>.

### -param Length 

[out]
A ULONG variable that receives  the length of the buffer pointer to by <i>TransferBuffer</i>.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The URB does not contain a transfer buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The transfer buffer MDL was not valid. 

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxurb/nf-udecxurb-udecxurbsetbytescompleted">UdecxUrbSetBytesCompleted</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
