---
UID: NF:sercx.SerCx2SystemDmaTransmitPurgeFifoComplete
title: SerCx2SystemDmaTransmitPurgeFifoComplete function (sercx.h)
description: The SerCx2SystemDmaTransmitPurgeFifoComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished purging the data from the transmit FIFO in the serial controller hardware.
old-location: serports\sercx2systemdmatransmitpurgefifocomplete.htm
tech.root: serports
ms.assetid: E1F0BB4A-17FB-4C35-9373-CD648553A738
ms.date: 04/23/2018
keywords: ["SerCx2SystemDmaTransmitPurgeFifoComplete function"]
ms.keywords: 2/SerCx2SystemDmaTransmitPurgeFifoComplete, SerCx2SystemDmaTransmitPurgeFifoComplete, SerCx2SystemDmaTransmitPurgeFifoComplete method [Serial Ports], serports.sercx2systemdmatransmitpurgefifocomplete
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SerCx2SystemDmaTransmitPurgeFifoComplete
 - sercx/SerCx2SystemDmaTransmitPurgeFifoComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2SystemDmaTransmitPurgeFifoComplete
---

# SerCx2SystemDmaTransmitPurgeFifoComplete function


## -description

The <b>SerCx2SystemDmaTransmitPurgeFifoComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished purging the data from the transmit FIFO in the serial controller hardware.

## -parameters

### -param SystemDmaTransmit 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method to create this object.

### -param BytesPurged 

[in]
The number of bytes of unsent data that the serial controller driver purged from the transmit FIFO.

## -remarks

SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a> event callback function, if it is implemented, to tell the serial controller driver to terminate the current system-DMA-transmit transaction. SerCx2 previously initiated this transaction in response to a write (<a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request from a client. For example, SerCx2 might call this function if the client cancels the pending write request, or if the write request times out. For more information, see <a href="/previous-versions/hh406672(v=vs.85)">SerCx2 Handling of Read and Write Requests</a>.

In response to the <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> call, the driver stops the transfer of data from the write buffer to the transmit FIFO, and discards any previously transferred data that remains in the transmit FIFO. After the purge finishes, the serial controller driver must call <b>SerCx2SystemDmaTransmitPurgeFifoComplete</b> to notify SerCx2. SerCx2 expects this notification and does not complete the write request until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaTransmitPurgeFifoComplete</b> only in response to a call to the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a> function.

SerCx2 uses the <i>BytesPurged</i> parameter value to determine how many bytes were successfully transmitted before the transmit FIFO was purged. SerCx2 requires this information to complete a write request that times out, or a write request that is canceled after one or more bytes are transmitted.

For more information, see <a href="/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transactions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a>



<a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>