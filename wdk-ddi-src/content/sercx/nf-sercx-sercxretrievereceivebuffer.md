---
UID: NF:sercx.SerCxRetrieveReceiveBuffer
title: SerCxRetrieveReceiveBuffer function
author: windows-driver-content
description: The SerCxRetrieveReceiveBuffer method obtains an input buffer into which data received from the serial port can be loaded.
old-location: serports\sercxretrievereceivebuffer.htm
old-project: serports
ms.assetid: 4EC1935D-038C-418C-AB28-A49085877B4A
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1/SerCxRetrieveReceiveBuffer, SerCxRetrieveReceiveBuffer, SerCxRetrieveReceiveBuffer method [Serial Ports], serports.sercxretrievereceivebuffer
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	1.0\Sercx.h
api_name:
-	SerCxRetrieveReceiveBuffer
product:
- Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCxRetrieveReceiveBuffer function


## -description


The <b>SerCxRetrieveReceiveBuffer</b> method obtains an input buffer into which data received from the serial port can be loaded.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Length [in]

The requested buffer length, in bytes. If the <b>SerCxRetrieveReceiveBuffer</b> call succeeds, the caller receives an input buffer that contains up to <i>Length</i> bytes of available space. (The available space in the buffer might be less than <i>Length</i> bytes.) <b>SerCxRetrieveReceiveBuffer</b> writes the actual number of bytes of available space to the <b>Length</b> member of the structure pointed to by the <i>BufferDescriptor</i> parameter.


### -param BufferDescriptor [in, out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439539">SERCX_BUFFER_DESCRIPTOR</a> structure. This structure describes the data buffer to use for the receive operation. The caller previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439542">SERCX_BUFFER_DESCRIPTOR_INIT</a> function to initialize this structure. <b>SerCxRetrieveTransmitBuffer</b> writes to the <b>Buffer</b> and <b>Length</b> members of this structure.


## -returns



<b>SerCxRetrieveReceiveBuffer</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The method was called at the wrong IRQL; or the WDFDEVICE handle is not valid; or either <i>Device</i> or <i>BufferDescriptor</i> is NULL; or the driver already has a receive buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The wrong size is specified for the <b>SERCX_BUFFER_DESCRIPTOR</b> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Could not allocate system resources (typically memory).

</td>
</tr>
</table>
 




## -remarks



The serial controller driver calls this method to acquire a buffer to contain input data from the current receive (read) operation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439539">SERCX_BUFFER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439542">SERCX_BUFFER_DESCRIPTOR_INIT</a>
 

 

