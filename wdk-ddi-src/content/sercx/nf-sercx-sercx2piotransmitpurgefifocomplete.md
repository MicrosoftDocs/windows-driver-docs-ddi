---
UID: NF:sercx.SerCx2PioTransmitPurgeFifoComplete
title: SerCx2PioTransmitPurgeFifoComplete function (sercx.h)
description: The SerCx2PioTransmitPurgeFifoComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished purging the data from the transmit FIFO in the serial controller hardware.
old-location: serports\sercx2piotransmitpurgefifocomplete.htm
tech.root: serports
ms.assetid: D5877A1C-0963-4C11-B440-122182CBA624
ms.date: 04/23/2018
ms.keywords: 2/SerCx2PioTransmitPurgeFifoComplete, SerCx2PioTransmitPurgeFifoComplete, SerCx2PioTransmitPurgeFifoComplete method [Serial Ports], serports.sercx2piotransmitpurgefifocomplete
ms.topic: function
f1_keywords:
 - "sercx/SerCx2PioTransmitPurgeFifoComplete"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2PioTransmitPurgeFifoComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2PioTransmitPurgeFifoComplete function


## -description


The <b>SerCx2PioTransmitPurgeFifoComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished purging the data from the transmit FIFO in the serial controller hardware.


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method to create this object.


### -param BytesPurged [in]

The number of bytes of unsent data that the serial controller driver purged from the transmit FIFO.


## -returns



None.




## -remarks



SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_pio_transmit_purge_fifo">EvtSerCx2PioTransmitPurgeFifo</a> event callback function, if it is implemented, to end the current PIO-transmit transaction. SerCx2 previously initiated this transaction in response to a write (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request from a client. For example, SerCx2 might call this function if the client cancels the pending write request, or the write request times out. For more information, see <a href="https://docs.microsoft.com/previous-versions/hh406672(v=vs.85)">SerCx2 Handling of Read and Write Requests</a>.

In response to the <i>EvtSerCx2PioTransmitPurgeFifo</i> function call, the driver first discards any data that remains in the transmit FIFO; then the driver must call <b>SerCx2PioTransmitPurgeFifoComplete</b> to notify SerCx2. SerCx2 expects this notification and does not complete the write request until it is notified.

The serial controller driver must call <b>SerCx2PioTransmitPurgeFifoComplete</b> only in response to a call to the <i>EvtSerCx2PioTransmitPurgeFifo</i> function.

SerCx2 uses the <i>BytesPurged</i> parameter value to determine how many bytes were successfully transmitted before the transmit FIFO was purged. SerCx2 requires this information to complete a write request that times out, or a write request that is canceled after one or more bytes are transmitted.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265336(v=vs.85)">SerCx2 PIO-Transmit Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_pio_transmit_purge_fifo">EvtSerCx2PioTransmitPurgeFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>
 

 

