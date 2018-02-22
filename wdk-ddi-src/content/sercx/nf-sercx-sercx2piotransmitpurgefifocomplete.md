---
UID: NF:sercx.SerCx2PioTransmitPurgeFifoComplete
title: SerCx2PioTransmitPurgeFifoComplete function
author: windows-driver-content
description: The SerCx2PioTransmitPurgeFifoComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished purging the data from the transmit FIFO in the serial controller hardware.
old-location: serports\sercx2piotransmitpurgefifocomplete.htm
old-project: serports
ms.assetid: D5877A1C-0963-4C11-B440-122182CBA624
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: serports.sercx2piotransmitpurgefifocomplete, SerCx2PioTransmitPurgeFifoComplete method [Serial Ports], SerCx2PioTransmitPurgeFifoComplete, 2/SerCx2PioTransmitPurgeFifoComplete
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
-	SerCx2PioTransmitPurgeFifoComplete
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCx2PioTransmitPurgeFifoComplete function


## -description


The <b>SerCx2PioTransmitPurgeFifoComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished purging the data from the transmit FIFO in the serial controller hardware.


## -syntax


````
VOID SerCx2PioTransmitPurgeFifoComplete(
  [in] SERCX2PIOTRANSMIT PioTransmit,
  [in] ULONG             BytesPurged
);
````


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


### -param BytesPurged [in]

The number of bytes of unsent data that the serial controller driver purged from the transmit FIFO.


## -returns



None.




## -remarks



SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_purge_fifo.md">EvtSerCx2PioTransmitPurgeFifo</a> event callback function, if it is implemented, to end the current PIO-transmit transaction. SerCx2 previously initiated this transaction in response to a write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request from a client. For example, SerCx2 might call this function if the client cancels the pending write request, or the write request times out. For more information, see <a href="https://msdn.microsoft.com/98100680-7D27-42B7-A445-C539B2DF95AD">SerCx2 Handling of Read and Write Requests</a>.

In response to the <i>EvtSerCx2PioTransmitPurgeFifo</i> function call, the driver first discards any data that remains in the transmit FIFO; then the driver must call <b>SerCx2PioTransmitPurgeFifoComplete</b> to notify SerCx2. SerCx2 expects this notification and does not complete the write request until it is notified.

The serial controller driver must call <b>SerCx2PioTransmitPurgeFifoComplete</b> only in response to a call to the <i>EvtSerCx2PioTransmitPurgeFifo</i> function.

SerCx2 uses the <i>BytesPurged</i> parameter value to determine how many bytes were successfully transmitted before the transmit FIFO was purged. SerCx2 requires this information to complete a write request that times out, or a write request that is canceled after one or more bytes are transmitted.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.




## -see-also

<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>



<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_purge_fifo.md">EvtSerCx2PioTransmitPurgeFifo</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_purge_fifo.md">EvtSerCx2PioTransmitPurgeFifo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2PioTransmitPurgeFifoComplete method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

