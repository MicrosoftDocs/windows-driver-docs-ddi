---
UID: NF:sercx.SerCx2PioReceiveReady
title: SerCx2PioReceiveReady function
author: windows-driver-content
description: The SerCx2PioReceiveReady method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller.
old-location: serports\sercx2pioreceiveready.htm
old-project: serports
ms.assetid: 81DE84F8-7D2D-464F-BA5D-4D92D0EE9149
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SerCx2PioReceiveReady method [Serial Ports], serports.sercx2pioreceiveready, SerCx2PioReceiveReady, 2/SerCx2PioReceiveReady
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	2.0\Sercx.h
apiname:
-	SerCx2PioReceiveReady
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2PioReceiveReady function


## -description


The <b>SerCx2PioReceiveReady</b> method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller.


## -syntax


````
VOID SerCx2PioReceiveReady(
  [in] SERCX2PIORECEIVE PioReceive
);
````


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method to create this object.


## -returns



None.




## -remarks



To initiate a PIO-receive transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a> event callback function and supplies a read buffer to which to transfer the data from the receive FIFO in the serial controller. If the return value from this function indicates that the read buffer was only partially filled before the receive FIFO became empty, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_enable_ready_notification.md">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback routine to enable a ready notification to occur when more data is available to be read.

If the ready notification is enabled and more data is available to be read, the serial controller driver must call <b>SerCx2PioReceiveReady</b> to notify SerCx2. In response to this notification, SerCx2 calls the <i>EvtSerCx2PioReceiveReadBuffer</i> function again to transfer more data from the receive FIFO to the read buffer.

The serial controller driver must call <b>SerCx2PioReceiveReady</b> only in response to a call to the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function.

Additionally, SerCx2 uses these ready notifications to detect interval time-outs during the handling of a read request. For more information about interval time-outs, see <a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>. For more information about ready notifications, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a>



<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>



<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2PioReceiveReady method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

