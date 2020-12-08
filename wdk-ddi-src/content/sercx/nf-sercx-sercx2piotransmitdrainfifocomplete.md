---
UID: NF:sercx.SerCx2PioTransmitDrainFifoComplete
title: SerCx2PioTransmitDrainFifoComplete function (sercx.h)
description: The SerCx2PioTransmitDrainFifoComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished draining the data from the transmit FIFO in the serial controller hardware.
old-location: serports\sercx2piotransmitdrainfifocomplete.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SerCx2PioTransmitDrainFifoComplete function"]
ms.keywords: 2/SerCx2PioTransmitDrainFifoComplete, SerCx2PioTransmitDrainFifoComplete, SerCx2PioTransmitDrainFifoComplete method [Serial Ports], serports.sercx2piotransmitdrainfifocomplete
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
 - SerCx2PioTransmitDrainFifoComplete
 - sercx/SerCx2PioTransmitDrainFifoComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2PioTransmitDrainFifoComplete
---

# SerCx2PioTransmitDrainFifoComplete function


## -description

The <b>SerCx2PioTransmitDrainFifoComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished draining the data from the transmit FIFO in the serial controller hardware.

## -parameters

### -param PioTransmit 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method to create this object.

## -remarks

SerCx2 calls the <b>SerCx2PioTransmitDrainFifoComplete</b> event callback function, if it is implemented, to drain the transmit FIFO at the end of a PIO-transmit transaction. This function makes sure that any data bytes that remain in the FIFO are transmitted from the serial port before SerCx2 completes the write (<a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request that initiated the transaction. After the last byte is transmitted from the FIFO, the serial controller driver must call the <b>SerCx2PioTransmitDrainFifoComplete</b> method to notify SerCx2. SerCx2 expects this notification and does not complete the write request until it is notified.

The serial controller driver must call <b>SerCx2PioTransmitDrainFifoComplete</b> only in response to a call to the <i>EvtSerCx2PioTransmitDrainFifo</i> function.

For more information, see <a href="/previous-versions/dn265336(v=vs.85)">SerCx2 PIO-Transmit Transactions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_drain_fifo">EvtSerCx2PioTransmitDrainFifo</a>



<a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>
