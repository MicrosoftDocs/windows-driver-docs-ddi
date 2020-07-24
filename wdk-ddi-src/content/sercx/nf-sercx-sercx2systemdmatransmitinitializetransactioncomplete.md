---
UID: NF:sercx.SerCx2SystemDmaTransmitInitializeTransactionComplete
title: SerCx2SystemDmaTransmitInitializeTransactionComplete function (sercx.h)
description: The SerCx2SystemDmaTransmitInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new system-DMA-transmit transaction.
old-location: serports\sercx2systemdmatransmitinitializetransactioncomplete.htm
tech.root: serports
ms.assetid: B5FDD4A4-2E43-4EAD-A475-A91C60A2E925
ms.date: 04/23/2018
keywords: ["SerCx2SystemDmaTransmitInitializeTransactionComplete function"]
ms.keywords: 2/SerCx2SystemDmaTransmitInitializeTransactionComplete, SerCx2SystemDmaTransmitInitializeTransactionComplete, SerCx2SystemDmaTransmitInitializeTransactionComplete method [Serial Ports], serports.sercx2systemdmatransmitinitializetransactioncomplete
f1_keywords:
 - "sercx/SerCx2SystemDmaTransmitInitializeTransactionComplete"
 - "SerCx2SystemDmaTransmitInitializeTransactionComplete"
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
- SerCx2SystemDmaTransmitInitializeTransactionComplete
targetos: Windows
req.typenames: 
---

# SerCx2SystemDmaTransmitInitializeTransactionComplete function


## -description


The <b>SerCx2SystemDmaTransmitInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new system-DMA-transmit transaction.


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -remarks



Before SerCx2 starts a system-DMA-transmit transaction, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_initialize_transaction">EvtSerCx2SystemDmaTransmitInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should do any initialization that is needed; then the driver must call <b>SerCx2SystemDmaTransmitInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaTransmitInitializeTransactionComplete</b> only in response to a call to the <i>EvtSerCx2SystemDmaTransmitInitializeTransaction</i> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transaction</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_initialize_transaction">EvtSerCx2SystemDmaTransmitInitializeTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>
 

 

