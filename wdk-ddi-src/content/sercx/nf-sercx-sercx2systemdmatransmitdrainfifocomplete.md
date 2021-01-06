---
UID: NF:sercx.SerCx2SystemDmaTransmitDrainFifoComplete
title: SerCx2SystemDmaTransmitDrainFifoComplete function (sercx.h)
description: The SerCx2SystemDmaTransmitDrainFifoComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished draining the data from the transmit FIFO in the serial controller hardware.
old-location: serports\sercx2systemdmatransmitdrainfifocomplete.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SerCx2SystemDmaTransmitDrainFifoComplete function"]
ms.keywords: 2/SerCx2SystemDmaTransmitDrainFifoComplete, SerCx2SystemDmaTransmitDrainFifoComplete, SerCx2SystemDmaTransmitDrainFifoComplete method [Serial Ports], serports.sercx2systemdmatransmitdrainfifocomplete
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
 - SerCx2SystemDmaTransmitDrainFifoComplete
 - sercx/SerCx2SystemDmaTransmitDrainFifoComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2SystemDmaTransmitDrainFifoComplete
---

# SerCx2SystemDmaTransmitDrainFifoComplete function


## -description

The <b>SerCx2SystemDmaTransmitDrainFifoComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished draining the data from the transmit FIFO in the serial controller hardware.

## -parameters

### -param SystemDmaTransmit

<p>A <a href="/windows-hardware/drivers/serports/sercx2-object-handles"><b>SERCX2SYSTEMDMATRANSMIT</b></a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate"><b>SerCx2SystemDmaTransmitCreate</b></a> method to create this object.</p>

## -remarks

SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a> event callback function, if it is implemented, to drain the transmit FIFO at the end of a system-DMA-transmit transaction. This function makes sure that any data bytes that remain in the FIFO are transmitted from the serial port before SerCx2 completes the write (<a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request that initiated the transaction. After the last byte is transmitted from the FIFO, the serial controller driver must call the <b>SerCx2SystemDmaTransmitDrainFifoComplete</b> method to notify SerCx2. SerCx2 expects this notification and does not complete the write request until it is notified.

The serial controller must call <b>SerCx2SystemDmaTransmitDrainFifoComplete</b> only in response to a call to the <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function.

For more information, see <a href="/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transactions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>
