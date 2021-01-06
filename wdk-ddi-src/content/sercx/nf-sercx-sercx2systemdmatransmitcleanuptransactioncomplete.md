---
UID: NF:sercx.SerCx2SystemDmaTransmitCleanupTransactionComplete
title: SerCx2SystemDmaTransmitCleanupTransactionComplete function (sercx.h)
description: The SerCx2SystemDmaTransmitCleanupTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a system-DMA-transmit transaction.
old-location: serports\sercx2systemdmatransmitcleanuptransactioncomplete.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SerCx2SystemDmaTransmitCleanupTransactionComplete function"]
ms.keywords: 2/SerCx2SystemDmaTransmitCleanupTransactionComplete, SerCx2SystemDmaTransmitCleanupTransactionComplete, SerCx2SystemDmaTransmitCleanupTransactionComplete method [Serial Ports], serports.sercx2systemdmatransmitcleanuptransactioncomplete
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
 - SerCx2SystemDmaTransmitCleanupTransactionComplete
 - sercx/SerCx2SystemDmaTransmitCleanupTransactionComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2SystemDmaTransmitCleanupTransactionComplete
---

# SerCx2SystemDmaTransmitCleanupTransactionComplete function


## -description

The <b>SerCx2SystemDmaTransmitCleanupTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a system-DMA-transmit transaction.

## -parameters

### -param SystemDmaTransmit 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method to create this object.

## -remarks

After a system-DMA-transmit transaction ends, SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cleanup_transaction">EvtSerCx2SystemDmaTransmitCleanupTransaction</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should do any clean-up work that is needed; then the driver must call <b>SerCx2SystemDmaTransmitCleanupTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaTransmitCleanupTransactionComplete</b> only in response to a call to the <i>EvtSerCx2SystemDmaTransmitCleanupTransaction</i> function.

For more information, see <a href="/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transaction</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cleanup_transaction">EvtSerCx2SystemDmaTransmitCleanupTransaction</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>
