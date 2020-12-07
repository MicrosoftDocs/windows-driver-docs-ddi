---
UID: NF:sercx.SerCx2PioTransmitInitializeTransactionComplete
title: SerCx2PioTransmitInitializeTransactionComplete function (sercx.h)
description: The SerCx2PioTransmitInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new PIO-transmit transaction.
old-location: serports\sercx2piotransmitinitializetransactioncomplete.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SerCx2PioTransmitInitializeTransactionComplete function"]
ms.keywords: 2/SerCx2PioTransmitInitializeTransactionComplete, SerCx2PioTransmitInitializeTransactionComplete, SerCx2PioTransmitInitializeTransactionComplete method [Serial Ports], serports.sercx2piotransmitinitializetransactioncomplete
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
 - SerCx2PioTransmitInitializeTransactionComplete
 - sercx/SerCx2PioTransmitInitializeTransactionComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2PioTransmitInitializeTransactionComplete
---

# SerCx2PioTransmitInitializeTransactionComplete function


## -description

The <b>SerCx2PioTransmitInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new PIO-transmit transaction.

## -parameters

### -param PioTransmit 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method to create this object.

### -param InitSuccess 

[in]
Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.

## -remarks

Before SerCx2 initiates a PIO-transmit transaction, SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_initialize_transaction">EvtSerCx2PioTransmitInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2PioTransmitInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2PioTransmitInitializeTransactionComplete</b> only in response to a call to the <i>EvtSerCx2PioTransmitInitializeTransaction</i> function.

For more information, see <a href="/previous-versions/dn265336(v=vs.85)">SerCx2 PIO-Transmit Transactions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_initialize_transaction">EvtSerCx2PioTransmitInitializeTransaction</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>
