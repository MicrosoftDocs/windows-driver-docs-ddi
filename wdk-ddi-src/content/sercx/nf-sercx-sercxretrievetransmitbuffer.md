---
UID: NF:sercx.SerCxRetrieveTransmitBuffer
title: SerCxRetrieveTransmitBuffer function
author: windows-driver-content
description: The SerCxRetrieveTransmitBuffer method obtains an output buffer that contains data that is ready to be transmitted to the serial port.
old-location: serports\sercxretrievetransmitbuffer.htm
old-project: serports
ms.assetid: 64494AB9-6F7F-4374-9081-8D65BA7D34E1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.sercxretrievetransmitbuffer, 1/SerCxRetrieveTransmitBuffer, SerCxRetrieveTransmitBuffer, SerCxRetrieveTransmitBuffer method [Serial Ports]
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
-	SerCxRetrieveTransmitBuffer
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCxRetrieveTransmitBuffer function


## -description


The <b>SerCxRetrieveTransmitBuffer</b> method obtains an output buffer that contains data that is ready to be transmitted to the serial port.


## -syntax


````
NTSTATUS SerCxRetrieveTransmitBuffer(
  [in]      WDFDEVICE                Device,
  [in]      ULONG                    Length,
  [in, out] PSERCX_BUFFER_DESCRIPTOR BufferDescriptor
);
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Length [in]

The requested buffer length, in bytes. If the <b>SerCxRetrieveTransmitBuffer</b> call succeeds, the caller receives an output buffer that contains up to <i>Length</i> bytes of available data. (The available data in the buffer might be less than <i>Length</i> bytes.) <b>SerCxRetrieveTransmitBuffer</b> writes the actual number of bytes of available data to the <b>Length</b> member of the structure pointed to by the <i>BufferDescriptor</i> parameter.


### -param BufferDescriptor [in, out]

A pointer to a caller-allocated <a href="..\sercx\ns-sercx-sercx_buffer_descriptor.md">SERCX_BUFFER_DESCRIPTOR</a> structure. This structure describes the data buffer to use for the transmit operation. The caller previously called the <a href="..\sercx\nf-sercx-sercx_buffer_descriptor_init.md">SERCX_BUFFER_DESCRIPTOR_INIT</a> function to initialize this structure. <b>SerCxRetrieveTransmitBuffer</b> writes to the <b>Buffer</b> and <b>Length</b> members of this structure.


## -returns



<b>SerCxRetrieveTransmitBuffer</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.

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
The method was called at the wrong IRQL; or the WDFDEVICE handle is not valid; or either <i>Device</i> or <i>BufferDescriptor</i> is NULL; or the driver already has a transmit buffer.

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



The serial controller driver calls this method to acquire a buffer that contains the output data for the current transmit (write) operation.




## -see-also

<a href="..\sercx\ns-sercx-sercx_buffer_descriptor.md">SERCX_BUFFER_DESCRIPTOR</a>



<a href="..\sercx\nf-sercx-sercx_buffer_descriptor_init.md">SERCX_BUFFER_DESCRIPTOR_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxRetrieveTransmitBuffer method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

