---
UID: NF:sercx.SerCx2SystemDmaTransmitPurgeFifoComplete
title: SerCx2SystemDmaTransmitPurgeFifoComplete function
author: windows-driver-content
description: The SerCx2SystemDmaTransmitPurgeFifoComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished purging the data from the transmit FIFO in the serial controller hardware.
old-location: serports\sercx2systemdmatransmitpurgefifocomplete.htm
old-project: serports
ms.assetid: E1F0BB4A-17FB-4C35-9373-CD648553A738
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2SystemDmaTransmitPurgeFifoComplete, serports.sercx2systemdmatransmitpurgefifocomplete, 2/SerCx2SystemDmaTransmitPurgeFifoComplete, SerCx2SystemDmaTransmitPurgeFifoComplete method [Serial Ports]
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
-	SerCx2SystemDmaTransmitPurgeFifoComplete
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCx2SystemDmaTransmitPurgeFifoComplete function


## -description


The <b>SerCx2SystemDmaTransmitPurgeFifoComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished purging the data from the transmit FIFO in the serial controller hardware.


## -syntax


````
VOID SerCx2SystemDmaTransmitPurgeFifoComplete(
  [in] SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit,
  [in] ULONG                   BytesPurged
);
````


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method to create this object.


### -param BytesPurged [in]

The number of bytes of unsent data that the serial controller driver purged from the transmit FIFO.


## -returns


None.



## -remarks


SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a> event callback function, if it is implemented, to tell the serial controller driver to terminate the current system-DMA-transmit transaction. SerCx2 previously initiated this transaction in response to a write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request from a client. For example, SerCx2 might call this function if the client cancels the pending write request, or if the write request times out. For more information, see <a href="https://msdn.microsoft.com/98100680-7D27-42B7-A445-C539B2DF95AD">SerCx2 Handling of Read and Write Requests</a>.

In response to the <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> call, the driver stops the transfer of data from the write buffer to the transmit FIFO, and discards any previously transferred data that remains in the transmit FIFO. After the purge finishes, the serial controller driver must call <b>SerCx2SystemDmaTransmitPurgeFifoComplete</b> to notify SerCx2. SerCx2 expects this notification and does not complete the write request until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaTransmitPurgeFifoComplete</b> only in response to a call to the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a> function.

SerCx2 uses the <i>BytesPurged</i> parameter value to determine how many bytes were successfully transmitted before the transmit FIFO was purged. SerCx2 requires this information to complete a write request that times out, or a write request that is canceled after one or more bytes are transmitted.

For more information, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a>

<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SystemDmaTransmitPurgeFifoComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

