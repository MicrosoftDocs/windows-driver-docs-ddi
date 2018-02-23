---
UID: NS:sercx.SERCX_BUFFER_DESCRIPTOR
title: SERCX_BUFFER_DESCRIPTOR
author: windows-driver-content
description: The SERCX_BUFFER_DESCRIPTOR structure describes a data buffer for a receive operation or transmit operation.
old-location: serports\sercx_buffer_descriptor.htm
old-project: serports
ms.assetid: 0F13A5B2-CD35-4127-B2E3-F4027D098CB2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERCX_BUFFER_DESCRIPTOR, PSERCX_BUFFER_DESCRIPTOR structure pointer [Serial Ports], PSERCX_BUFFER_DESCRIPTOR, serports.sercx_buffer_descriptor, 1/SERCX_BUFFER_DESCRIPTOR, SERCX_BUFFER_DESCRIPTOR structure [Serial Ports], 1/PSERCX_BUFFER_DESCRIPTOR, SERCX_BUFFER_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1.0\Sercx.h
apiname:
-	SERCX_BUFFER_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: SERCX_BUFFER_DESCRIPTOR, *PSERCX_BUFFER_DESCRIPTOR
req.product: Windows 10 or later.
---

# SERCX_BUFFER_DESCRIPTOR structure


## -description


The <b>SERCX_BUFFER_DESCRIPTOR</b> structure describes a data buffer for a receive operation or transmit operation.


## -syntax


````
typedef struct _SERCX_BUFFER_DESCRIPTOR {
  USHORT Size;
  PUCHAR Buffer;
  ULONG  Length;
} SERCX_BUFFER_DESCRIPTOR, *PSERCX_BUFFER_DESCRIPTOR;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.  The <a href="..\sercx\nf-sercx-sercxretrievereceivebuffer.md">SerCxRetrieveReceiveBuffer</a> and <a href="..\sercx\nf-sercx-sercxretrievetransmitbuffer.md">SerCxRetrieveTransmitBuffer</a> methods use this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field Buffer

The virtual memory address of the buffer. The memory for the buffer is nonpaged.


### -field Length

The number of bytes available in the buffer. This size determines the maximize number of bytes that can be transferred by the receive or transmit operation.


## -remarks



The serial  controller driver uses the information in this structure to determine where in memory to read data from during a receive operation, and where in memory to write data during a transmit operation.

At any time, there can be no more than one valid receive buffer and one valid transmit buffer.  The controller driver calls the <a href="..\sercx\nf-sercx-sercxretrievereceivebuffer.md">SerCxRetrieveReceiveBuffer</a> method to obtain the receive buffer, and calls the <a href="..\sercx\nf-sercx-sercxretrievetransmitbuffer.md">SerCxRetrieveTransmitBuffer</a> method to obtain the transmit buffer.  Both methods copy buffer descriptions into caller-allocated <b>SERCX_BUFFER_DESCRIPTOR</b> structures. A subsequent call to one of these methods invalidates the previously issued descriptor for the receive buffer or transmit buffer, respectively.  The caller must not access a buffer that is described by a buffer descriptor that is no longer valid.

The buffers that are obtained by successive calls to <b>SerCxRetrieveReceiveBuffer</b> or <b>SerCxRetrieveTransmitBuffer</b> are not guaranteed to be contiguous.

The controller driver must call the <a href="..\sercx\nf-sercx-sercx_buffer_descriptor_init.md">SERCX_BUFFER_DESCRIPTOR_INIT</a> function to initialize an <b>SERCX_BUFFER_DESCRIPTOR</b> structure before the structure is passed to the <a href="..\sercx\nf-sercx-sercxretrievereceivebuffer.md">SerCxRetrieveReceiveBuffer</a> or <a href="..\sercx\nf-sercx-sercxretrievetransmitbuffer.md">SerCxRetrieveTransmitBuffer</a> method. After a buffer descriptor is initialized, it can be reused without being initialized again.




## -see-also

<a href="..\sercx\nf-sercx-sercxretrievereceivebuffer.md">SerCxRetrieveReceiveBuffer</a>



<a href="..\sercx\nf-sercx-sercxretrievetransmitbuffer.md">SerCxRetrieveTransmitBuffer</a>



<a href="..\sercx\nf-sercx-sercx_buffer_descriptor_init.md">SERCX_BUFFER_DESCRIPTOR_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX_BUFFER_DESCRIPTOR structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

