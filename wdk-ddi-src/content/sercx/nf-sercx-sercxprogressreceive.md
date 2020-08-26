---
UID: NF:sercx.SerCxProgressReceive
title: SerCxProgressReceive function (sercx.h)
description: The SerCxProgressReceive method reports the progress of the current read (receive) operation.
old-location: serports\sercxprogressreceive.htm
tech.root: serports
ms.assetid: A1773CCB-971E-4439-A11F-82761FF8AF71
ms.date: 04/23/2018
keywords: ["SerCxProgressReceive function"]
ms.keywords: 1/SerCxProgressReceive, SerCxProgressReceive, SerCxProgressReceive method [Serial Ports], serports.sercxprogressreceive
f1_keywords:
 - "sercx/SerCxProgressReceive"
 - "SerCxProgressReceive"
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 1.0\Sercx.h
api_name:
- SerCxProgressReceive
targetos: Windows
req.typenames: 
---

# SerCxProgressReceive function


## -description


The <b>SerCxProgressReceive</b> method reports the progress of the current read (receive) operation.


## -parameters




### -param Device 
[in]
A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param BytesReceived 
[in]
The number of bytes of data that the caller loaded into the receive buffer that was obtained by the latest call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxretrievereceivebuffer">SerCxRetrieveReceiveBuffer</a> method.


### -param ReceiveStatus 
[in]
The current status of the receive operation. Set this parameter to one of the following values:

<ul>
<li><b>SerCxStatusSuccess</b></li>
<li><b>SerCxStatusCancelled</b></li>
<li><b>SerCxStatusTimeout</b></li>
</ul>
For more information about these values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ne-sercx-_sercx_status">SERCX_STATUS</a>.


## -returns



<b>SerCxProgressReceive</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.

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
The <i>BytesReceived</i> value exceeds the available buffer length; or the <i>ReceiveStatus</i> value is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The method was called at the wrong IRQL; or the WDFDEVICE handle is not valid; or the driver has not obtained an input buffer for this receive operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The receive operation has already been canceled.

</td>
</tr>
</table>
 




## -remarks



The serial controller driver calls this method to report progress on an outstanding read operation. Typically, the serial controller driver calls this method from its DMA completion callback (if the driver uses DMA to read the data) or from its transmit/receive DPC function (if PIO is used).

If the <b>SerCxProgressReceive</b> does not complete all outstanding work for the read operation, the caller must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxretrievereceivebuffer">SerCxRetrieveReceiveBuffer</a> method again to get a new buffer descriptor and continue to receive data.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ne-sercx-_sercx_status">SERCX_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxretrievereceivebuffer">SerCxRetrieveReceiveBuffer</a>
 

 

