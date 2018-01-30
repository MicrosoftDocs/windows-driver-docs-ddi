---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO
author: windows-driver-content
description: The EvtSerCx2SystemDmaTransmitCancelDrainFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a previous request to drain the transmit FIFO in the serial controller hardware.
old-location: serports\evtsercx2systemdmatransmitcanceldrainfifo.htm
old-project: serports
ms.assetid: 00B17CBC-FE0E-4611-A41B-42AD833731D3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2systemdmatransmitcanceldrainfifo, EvtSerCx2SystemDmaTransmitCancelDrainFifo callback function [Serial Ports], EvtSerCx2SystemDmaTransmitCancelDrainFifo, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO, 2/EvtSerCx2SystemDmaTransmitCancelDrainFifo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	2.0\Sercx.h
apiname:
-	EvtSerCx2SystemDmaTransmitCancelDrainFifo
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO callback


## -description


The <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a previous request to drain the transmit FIFO in the serial controller hardware.


## -prototype


````
EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO EvtSerCx2SystemDmaTransmitCancelDrainFifo;

BOOLEAN EvtSerCx2SystemDmaTransmitCancelDrainFifo(
  _In_ SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit
)
{ ... }
````


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method to create this object.


## -returns


The <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> function returns <b>TRUE</b> if it successfully cancels the pending drain request, and the serial controller driver can guarantee that it will not call the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitdrainfifocomplete.md">SerCx2SystemDmaTransmitDrainFifoComplete</a> method to notify SerCx2 that the FIFO is drained. Otherwise, this function returns <b>FALSE</b> to indicate that the driver has already called or is about to call <b>SerCx2SystemDmaTransmitDrainFifoComplete</b>.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

Your driver should implement an <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> function if the serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data. If your driver implements this function, it must also implement the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo.md">EvtSerCx2SystemDmaTransmitDrainFifo</a> and <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a> event callback functions.

After SerCx2 calls the <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> event callback function to request that the serial controller driver drain the transmit FIFO, SerCx2 might call the <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> function to cancel the pending drain request before the FIFO finishes draining. For example, SerCx2 might call the <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> function if the client cancels the pending write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request, or if the write request times out.

For more information, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2systemdmatransmitdrainfifocomplete.md">SerCx2SystemDmaTransmitDrainFifoComplete</a>

<a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a>

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo.md">EvtSerCx2SystemDmaTransmitDrainFifo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

