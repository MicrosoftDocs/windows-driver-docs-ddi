---
UID: NF:sercx.SerCxGetRingBufferUtilization
title: SerCxGetRingBufferUtilization function
author: windows-driver-content
description: The SerCxGetRingBufferUtilization method enables the serial controller driver to determine how much of the type-ahead ring buffer is currently filled by data received from the serial port.
old-location: serports\sercxgetringbufferutilization.htm
old-project: serports
ms.assetid: 8D4B8682-5713-47D6-A18E-F2EE44614DFB
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1/SerCxGetRingBufferUtilization, SerCxGetRingBufferUtilization, SerCxGetRingBufferUtilization method [Serial Ports], serports.sercxgetringbufferutilization
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
-	SerCxGetRingBufferUtilization
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCxGetRingBufferUtilization function


## -description


The <b>SerCxGetRingBufferUtilization</b> method enables the serial controller driver to determine how much of the type-ahead ring buffer is currently filled by data received from the serial port.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param BytesUsed [out, optional]

The number of bytes of unread data that are currently contained in the type-ahead ring buffer that is used to store received data.


### -param BufferSize [out, optional]

The size, in bytes, of the type-ahead ring buffer that is used to store received data.


## -returns



None.




## -remarks



The serial controller driver calls this function to determine how much storage space is available in the type-ahead ring buffer. The serial controller extension (SerCx) maintains this buffer to contain data that the serial controller driver receives from the serial port when no read request from the client is currently being processed. This function provides the information that the driver requires to accurately perform software flow control (XON/XOFF).

To implement software flow control, the serial controller driver monitors the amount of space available in the type-ahead ring buffer. The available space, in bytes, is equal to <i>BufferSize</i> - <i>BytesUsed</i>. When the available space falls below a client-specified threshold, <b>XoffLimit</b>, the serial controller driver transmits an XOFF character to tell the transmitting port to pause transmission. Later, when the available space rises above a client-specified threshold, <b>XonLimit</b>, the driver transmits an XON character to tell the transmitting port to resume transmission. Typically, the client specified these two thresholds in a previous <a href="https://msdn.microsoft.com/library/windows/hardware/ff546736">IOCTL_SERIAL_SET_HANDFLOW</a> I/O control request.

SerCx evaluates the available space in the type-ahead ring buffer in the context of the current flow control and handshaking settings. After the type-ahead ring buffer empties completely, SerCx calls the driver's <a href="https://msdn.microsoft.com/C862D632-5425-4EEB-9C5D-BC3721D9F132">EvtSerCxReceive</a> callback function so that the driver can send an XON and resume receiving data. The <i>EvtSerCxReceive</i> function can call <b>SerCxGetRingBufferUtilization</b> to determine whether to send an XON.




## -see-also




<a href="https://msdn.microsoft.com/C862D632-5425-4EEB-9C5D-BC3721D9F132">EvtSerCxReceive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546736">IOCTL_SERIAL_SET_HANDFLOW</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxGetRingBufferUtilization method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

