---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO (sercx.h)
description: The EvtSerCx2SystemDmaTransmitCancelDrainFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a previous request to drain the transmit FIFO in the serial controller hardware.
old-location: serports\evtsercx2systemdmatransmitcanceldrainfifo.htm
tech.root: serports
ms.assetid: 00B17CBC-FE0E-4611-A41B-42AD833731D3
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO callback function"]
ms.keywords: 2/EvtSerCx2SystemDmaTransmitCancelDrainFifo, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO callback, EvtSerCx2SystemDmaTransmitCancelDrainFifo, EvtSerCx2SystemDmaTransmitCancelDrainFifo callback function [Serial Ports], serports.evtsercx2systemdmatransmitcanceldrainfifo
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO
 - sercx/EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EvtSerCx2SystemDmaTransmitCancelDrainFifo
---

# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO callback function


## -description

The <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a previous request to drain the transmit FIFO in the serial controller hardware.

## -parameters

### -param SystemDmaTransmit 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method to create this object.

## -returns

The <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> function returns <b>TRUE</b> if it successfully cancels the pending drain request, and the serial controller driver can guarantee that it will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitdrainfifocomplete">SerCx2SystemDmaTransmitDrainFifoComplete</a> method to notify SerCx2 that the FIFO is drained. Otherwise, this function returns <b>FALSE</b> to indicate that the driver has already called or is about to call <b>SerCx2SystemDmaTransmitDrainFifoComplete</b>.

## -remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

Your driver should implement an <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> function if the serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data. If your driver implements this function, it must also implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a> event callback functions.

After SerCx2 calls the <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> event callback function to request that the serial controller driver drain the transmit FIFO, SerCx2 might call the <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> function to cancel the pending drain request before the FIFO finishes draining. For example, SerCx2 might call the <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> function if the client cancels the pending write (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request, or if the write request times out.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaTransmitCancelDrainFifo</i> callback function that is named <code>MySystemDmaTransmitCancelDrainFifo</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type, as shown in this code example:


```cpp
EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO  MySystemDmaTransmitCancelDrainFifo;
```

Then, implement your callback function as follows:


```cpp
_Use_decl_annotations_
BOOLEAN
  MySystemDmaTransmitCancelDrainFifo(
    SERCX2SYSTEMDMATRANSMIT  SystemDmaTransmit
    )
  {...}
```

The <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitdrainfifocomplete">SerCx2SystemDmaTransmitDrainFifoComplete</a>

