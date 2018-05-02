---
UID: NF:sercx.SerCx2PioReceiveReady
title: SerCx2PioReceiveReady function
author: windows-driver-content
description: The SerCx2PioReceiveReady method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller.
old-location: serports\sercx2pioreceiveready.htm
old-project: serports
ms.assetid: 81DE84F8-7D2D-464F-BA5D-4D92D0EE9149
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: 2/SerCx2PioReceiveReady, SerCx2PioReceiveReady, SerCx2PioReceiveReady method [Serial Ports], serports.sercx2pioreceiveready
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
-	2.0\Sercx.h
api_name:
-	SerCx2PioReceiveReady
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2PioReceiveReady function


## -description


The <b>SerCx2PioReceiveReady</b> method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller.


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> method to create this object.


## -returns



None.




## -remarks



To initiate a PIO-receive transaction, SerCx2 calls the <a href="https://msdn.microsoft.com/B69A128A-B1B0-47BC-9783-32780FC9C447">EvtSerCx2PioReceiveReadBuffer</a> event callback function and supplies a read buffer to which to transfer the data from the receive FIFO in the serial controller. If the return value from this function indicates that the read buffer was only partially filled before the receive FIFO became empty, SerCx2 calls the <a href="https://msdn.microsoft.com/DDD17DF3-9457-40D1-BE18-0A1CAED1389B">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback routine to enable a ready notification to occur when more data is available to be read.

If the ready notification is enabled and more data is available to be read, the serial controller driver must call <b>SerCx2PioReceiveReady</b> to notify SerCx2. In response to this notification, SerCx2 calls the <i>EvtSerCx2PioReceiveReadBuffer</i> function again to transfer more data from the receive FIFO to the read buffer.

The serial controller driver must call <b>SerCx2PioReceiveReady</b> only in response to a call to the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function.

Additionally, SerCx2 uses these ready notifications to detect interval time-outs during the handling of a read request. For more information about interval time-outs, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>. For more information about ready notifications, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.




## -see-also




<a href="https://msdn.microsoft.com/B69A128A-B1B0-47BC-9783-32780FC9C447">EvtSerCx2PioReceiveReadBuffer</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a>
 

 

