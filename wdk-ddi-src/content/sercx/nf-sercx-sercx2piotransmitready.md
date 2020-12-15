---
UID: NF:sercx.SerCx2PioTransmitReady
title: SerCx2PioTransmitReady function (sercx.h)
description: The SerCx2PioTransmitReady method notifies version 2 of the serial framework extension (SerCx2) that the transmit FIFO in the serial controller hardware is ready to accept more data.
old-location: serports\sercx2piotransmitready.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SerCx2PioTransmitReady function"]
ms.keywords: 2/SerCx2PioTransmitReady, SerCx2PioTransmitReady, SerCx2PioTransmitReady method [Serial Ports], serports.sercx2piotransmitready
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
 - SerCx2PioTransmitReady
 - sercx/SerCx2PioTransmitReady
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2PioTransmitReady
---

# SerCx2PioTransmitReady function


## -description

The <b>SerCx2PioTransmitReady</b> method notifies version 2 of the serial framework extension (SerCx2) that the transmit FIFO in the serial controller hardware is ready to accept more data.

## -parameters

### -param PioTransmit 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method to create this object.

## -remarks

To initiate a PIO-transmit transaction, SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_write_buffer">EvtSerCx2PioTransmitWriteBuffer</a> event callback function and supplies a write buffer that contains the data to be transmitted. If the return value from this call indicates that the transmit FIFO in the serial controller became full before the entire contents of the write buffer could be transmitted, SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function to enable a ready notification to occur when the FIFO is ready to accept more data.

If the ready notification is enabled, the serial controller driver must call <b>SerCx2PioTransmitReady</b> to notify SerCx2 after the transmit FIFO becomes ready to accept more data. In response to this notification, SerCx2 calls the <i>EvtSerCx2PioTransmitWriteBuffer</i> function again to transfer more data from the write buffer to the transmit FIFO.

The serial controller driver must call <b>SerCx2PioTransmitReady</b> only in response to a call to the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function.

For more information, see <a href="/previous-versions/dn265336(v=vs.85)">SerCx2 PIO-Transmit Transactions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification">EvtSerCx2PioTransmitEnableReadyNotification</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_write_buffer">EvtSerCx2PioTransmitWriteBuffer</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>
