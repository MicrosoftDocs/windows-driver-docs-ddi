---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO (sercx.h)
description: The EvtSerCx2SystemDmaTransmitPurgeFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to discard any bytes of unsent data that remain in the transmit FIFO in the serial controller hardware.
old-location: serports\evtsercx2systemdmatransmitpurgefifo.htm
tech.root: serports
ms.assetid: 79BD2B77-E99A-4CFA-9F7B-AFC984D5F0B3
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO callback function"]
ms.keywords: 2/EvtSerCx2SystemDmaTransmitPurgeFifo, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO callback, EvtSerCx2SystemDmaTransmitPurgeFifo, EvtSerCx2SystemDmaTransmitPurgeFifo callback function [Serial Ports], serports.evtsercx2systemdmatransmitpurgefifo
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
 - EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO
 - sercx/EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EvtSerCx2SystemDmaTransmitPurgeFifo
---

# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO callback function


## -description

The <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to discard any bytes of unsent data that remain in the transmit FIFO in the serial controller hardware.

## -parameters

### -param SystemDmaTransmit 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method to create this object.

### -param BytesAlreadyTransmittedToHardware 

[in]
The number of bytes that have already been loaded into the transmit FIFO during the current system-DMA-transmit transaction.

## -remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

Your driver should implement an <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> function if the serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data. If your driver implements this function, it must also implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a> event callback functions.

If a pending write (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request times out or is canceled, SerCx2 might need to terminate the current system-DMA transaction before it finishes. After the transaction is terminated, SerCx2 calls the <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> function, if it is implemented.

The <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> function halts the transfer of data from the write buffer to the transmit FIFO, and discards any previously transferred data that remains in the FIFO. After the transmit transaction is terminated, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitpurgefifocomplete">SerCx2SystemDmaTransmitPurgeFifoComplete</a> method to notify SerCx2 that the FIFO was purged, and SerCx2 then completes the write request.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> callback function that is named <code>MySystemDmaTransmitPurgeFifo</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO</b> function type, as shown in this code example:


```cpp
EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO  MySystemDmaTransmitPurgeFifo;
```

Then, implement your callback function as follows:


```cpp
_Use_decl_annotations_
VOID
  MySystemDmaTransmitPurgeFifo(
    SERCX2SYSTEMDMATRANSMIT  SystemDmaTransmit,
    ULONG BytesAlreadyTransmittedToHardware
    )
  {...}
```

The <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitpurgefifocomplete">SerCx2SystemDmaTransmitPurgeFifoComplete</a>

