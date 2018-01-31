---
UID: NF:sercx.SerCxProgressReceive
title: SerCxProgressReceive function
author: windows-driver-content
description: The SerCxProgressReceive method reports the progress of the current read (receive) operation.
old-location: serports\sercxprogressreceive.htm
old-project: serports
ms.assetid: A1773CCB-971E-4439-A11F-82761FF8AF71
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 1/SerCxProgressReceive, SerCxProgressReceive, serports.sercxprogressreceive, SerCxProgressReceive method [Serial Ports]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	1.0\Sercx.h
apiname:
-	SerCxProgressReceive
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCxProgressReceive function


## -description


The <b>SerCxProgressReceive</b> method reports the progress of the current read (receive) operation.


## -syntax


````
NTSTATUS SerCxProgressReceive(
  [in] WDFDEVICE    Device,
  [in] ULONG        BytesReceived,
  [in] SERCX_STATUS ReceiveStatus
);
````


## -parameters




#### - Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


#### - BytesReceived [in]

The number of bytes of data that the caller loaded into the receive buffer that was obtained by the latest call to the <a href="..\sercx\nf-sercx-sercxretrievereceivebuffer.md">SerCxRetrieveReceiveBuffer</a> method.


#### - ReceiveStatus [in]

The current status of the receive operation. Set this parameter to one of the following values:
<ul>
<li><b>SerCxStatusSuccess</b></li>
<li><b>SerCxStatusCancelled</b></li>
<li><b>SerCxStatusTimeout</b></li>
</ul>For more information about these values, see <a href="..\sercx\ne-sercx-_sercx_status.md">SERCX_STATUS</a>.


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

If the <b>SerCxProgressReceive</b> does not complete all outstanding work for the read operation, the caller must call the <a href="..\sercx\nf-sercx-sercxretrievereceivebuffer.md">SerCxRetrieveReceiveBuffer</a> method again to get a new buffer descriptor and continue to receive data.



## -see-also

<a href="..\sercx\ne-sercx-_sercx_status.md">SERCX_STATUS</a>

<a href="..\sercx\nf-sercx-sercxretrievereceivebuffer.md">SerCxRetrieveReceiveBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxProgressReceive method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

