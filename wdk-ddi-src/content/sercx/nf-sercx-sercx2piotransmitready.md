---
UID: NF:sercx.SerCx2PioTransmitReady
title: SerCx2PioTransmitReady function
author: windows-driver-content
description: The SerCx2PioTransmitReady method notifies version 2 of the serial framework extension (SerCx2) that the transmit FIFO in the serial controller hardware is ready to accept more data.
old-location: serports\sercx2piotransmitready.htm
old-project: serports
ms.assetid: 58E663DC-8A2B-4017-A54F-4C127AE567CE
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , 2, 2/SerCx2PioTransmitReady, C, P, R, S, SerCx2PioTransmitReady, SerCx2PioTransmitReady method [Serial Ports], T, a, d, e, i, m, n, o, r, s, serports.sercx2piotransmitready, t, x, y"
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
-	SerCx2PioTransmitReady
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2PioTransmitReady function


## -description


The <b>SerCx2PioTransmitReady</b> method notifies version 2 of the serial framework extension (SerCx2) that the transmit FIFO in the serial controller hardware is ready to accept more data.


## -syntax


````
VOID SerCx2PioTransmitReady(
  [in] SERCX2PIOTRANSMIT PioTransmit
);
````


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


## -returns



None.




## -remarks



To initiate a PIO-transmit transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_write_buffer.md">EvtSerCx2PioTransmitWriteBuffer</a> event callback function and supplies a write buffer that contains the data to be transmitted. If the return value from this call indicates that the transmit FIFO in the serial controller became full before the entire contents of the write buffer could be transmitted, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function to enable a ready notification to occur when the FIFO is ready to accept more data.

If the ready notification is enabled, the serial controller driver must call <b>SerCx2PioTransmitReady</b> to notify SerCx2 after the transmit FIFO becomes ready to accept more data. In response to this notification, SerCx2 calls the <i>EvtSerCx2PioTransmitWriteBuffer</i> function again to transfer more data from the write buffer to the transmit FIFO.

The serial controller driver must call <b>SerCx2PioTransmitReady</b> only in response to a call to the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.




## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_write_buffer.md">EvtSerCx2PioTransmitWriteBuffer</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2PioTransmitReady method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

