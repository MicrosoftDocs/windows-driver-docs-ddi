---
UID: NS:sercx.SERCX_BUFFER_DESCRIPTOR
title: SERCX_BUFFER_DESCRIPTOR
author: windows-driver-content
description: The SERCX_BUFFER_DESCRIPTOR structure describes a data buffer for a receive operation or transmit operation.
old-location: serports\sercx_buffer_descriptor.htm
old-project: serports
ms.assetid: 0F13A5B2-CD35-4127-B2E3-F4027D098CB2
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PSERCX_BUFFER_DESCRIPTOR, 1/PSERCX_BUFFER_DESCRIPTOR, 1/SERCX_BUFFER_DESCRIPTOR, PSERCX_BUFFER_DESCRIPTOR, PSERCX_BUFFER_DESCRIPTOR structure pointer [Serial Ports], SERCX_BUFFER_DESCRIPTOR, SERCX_BUFFER_DESCRIPTOR structure [Serial Ports], serports.sercx_buffer_descriptor"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1.0\Sercx.h
api_name:
-	SERCX_BUFFER_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: SERCX_BUFFER_DESCRIPTOR, *PSERCX_BUFFER_DESCRIPTOR
---

# SERCX_BUFFER_DESCRIPTOR structure


## -description


The <b>SERCX_BUFFER_DESCRIPTOR</b> structure describes a data buffer for a receive operation or transmit operation.


## -struct-fields




### -field Size

The size, in bytes, of this structure.  The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406718">SerCxRetrieveReceiveBuffer</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439519">SerCxRetrieveTransmitBuffer</a> methods use this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field Buffer

The virtual memory address of the buffer. The memory for the buffer is nonpaged.


### -field Length

The number of bytes available in the buffer. This size determines the maximize number of bytes that can be transferred by the receive or transmit operation.


## -remarks



The serial  controller driver uses the information in this structure to determine where in memory to read data from during a receive operation, and where in memory to write data during a transmit operation.

At any time, there can be no more than one valid receive buffer and one valid transmit buffer.  The controller driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406718">SerCxRetrieveReceiveBuffer</a> method to obtain the receive buffer, and calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439519">SerCxRetrieveTransmitBuffer</a> method to obtain the transmit buffer.  Both methods copy buffer descriptions into caller-allocated <b>SERCX_BUFFER_DESCRIPTOR</b> structures. A subsequent call to one of these methods invalidates the previously issued descriptor for the receive buffer or transmit buffer, respectively.  The caller must not access a buffer that is described by a buffer descriptor that is no longer valid.

The buffers that are obtained by successive calls to <b>SerCxRetrieveReceiveBuffer</b> or <b>SerCxRetrieveTransmitBuffer</b> are not guaranteed to be contiguous.

The controller driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439542">SERCX_BUFFER_DESCRIPTOR_INIT</a> function to initialize an <b>SERCX_BUFFER_DESCRIPTOR</b> structure before the structure is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406718">SerCxRetrieveReceiveBuffer</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh439519">SerCxRetrieveTransmitBuffer</a> method. After a buffer descriptor is initialized, it can be reused without being initialized again.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439542">SERCX_BUFFER_DESCRIPTOR_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406718">SerCxRetrieveReceiveBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439519">SerCxRetrieveTransmitBuffer</a>
 

 

