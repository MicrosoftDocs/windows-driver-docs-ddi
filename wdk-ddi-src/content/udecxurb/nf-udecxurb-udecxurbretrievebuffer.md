---
UID: NF:udecxurb.UdecxUrbRetrieveBuffer
title: UdecxUrbRetrieveBuffer function
author: windows-driver-content
description: Retrieves the transfer buffer of an URB from the specified framework request object sent to the endpoint queue.
old-location: buses\udecxurbretrievebuffer.htm
old-project: UsbRef
ms.assetid: C2AE51AE-EEB6-49BB-A6E4-BBCE6A25C905
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , B, R, U, UdecxUrbRetrieveBuffer, UdecxUrbRetrieveBuffer function [Buses], b, buses.udecxurbretrievebuffer, c, d, e, f, i, r, t, u, udecxurb/UdecxUrbRetrieveBuffer, v, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UdecxUrbRetrieveBuffer
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---

# UdecxUrbRetrieveBuffer function


## -description


Retrieves the transfer buffer of an URB from the specified framework request object sent to the endpoint queue.



## -syntax


````
FORCEINLINE NTSTATUS UdecxUrbRetrieveBuffer(
  _In_  WDFREQUEST                         Request,
  _Out_ ptr_result_buffer_(*Length) PUCHAR *TransferBuffer,
  _Out_ PULONG                             Length
);
````


## -parameters




### -param Request [in]

A handle to a framework request object that contains the <a href="..\usb\ns-usb-_urb.md">URB</a> for the transfer.


### -param TransferBuffer [out]

A pointer to a buffer that receives the transfer buffer of an <a href="..\usb\ns-usb-_urb.md">URB</a>.


### -param Length [out]

A ULONG variable that receives  the length of the buffer pointer to by <i>TransferBuffer</i>.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 

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

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="..\udecxurb\nf-udecxurb-udecxurbsetbytescompleted.md">UdecxUrbSetBytesCompleted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UdecxUrbRetrieveBuffer function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

