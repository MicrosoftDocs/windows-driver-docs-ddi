---
UID: NF:sercx.SerCx2SystemDmaReceiveInitializeTransactionComplete
title: SerCx2SystemDmaReceiveInitializeTransactionComplete function (sercx.h)
description: The SerCx2SystemDmaReceiveInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new system-DMA-receive transaction.
old-location: serports\sercx2systemdmareceiveinitializetransactioncomplete.htm
tech.root: serports
ms.assetid: B65DC4AD-FB24-4F1D-A1E9-F9B38160908E
ms.date: 04/23/2018
keywords: ["SerCx2SystemDmaReceiveInitializeTransactionComplete function"]
ms.keywords: 2/SerCx2SystemDmaReceiveInitializeTransactionComplete, SerCx2SystemDmaReceiveInitializeTransactionComplete, SerCx2SystemDmaReceiveInitializeTransactionComplete method [Serial Ports], serports.sercx2systemdmareceiveinitializetransactioncomplete
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
 - SerCx2SystemDmaReceiveInitializeTransactionComplete
 - sercx/SerCx2SystemDmaReceiveInitializeTransactionComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2SystemDmaReceiveInitializeTransactionComplete
---

# SerCx2SystemDmaReceiveInitializeTransactionComplete function


## -description

The <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new system-DMA-receive transaction.

## -parameters

### -param SystemDmaReceive 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method to create this object.

### -param InitSuccess 

[in]
Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.

## -remarks

Before SerCx2 initiates a system-DMA-receive transaction, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction">EvtSerCx2SystemDmaReceiveInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should do any initialization that is needed; then the driver must call <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> only in response to a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction">EvtSerCx2SystemDmaReceiveInitializeTransaction</a> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265343(v=vs.85)">SerCx2 System-DMA-Receive Transactions</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction">EvtSerCx2SystemDmaReceiveInitializeTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a>

