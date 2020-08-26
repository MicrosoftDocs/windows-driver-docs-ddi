---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO
title: EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO (sercx.h)
description: The EvtSerCx2PioTransmitPurgeFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to discard any bytes of unsent data that remain in the transmit FIFO in the serial controller.
old-location: serports\evtsercx2piotransmitpurgefifo.htm
tech.root: serports
ms.assetid: 2BB02F84-01C1-432D-A4A9-6035F3ED32D7
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO callback function"]
ms.keywords: 2/EvtSerCx2PioTransmitPurgeFifo, EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO, EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO callback, EvtSerCx2PioTransmitPurgeFifo, EvtSerCx2PioTransmitPurgeFifo callback function [Serial Ports], serports.evtsercx2piotransmitpurgefifo
f1_keywords:
 - "sercx/EvtSerCx2PioTransmitPurgeFifo"
 - "EvtSerCx2PioTransmitPurgeFifo"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2PioTransmitPurgeFifo
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO callback function


## -description


The <i>EvtSerCx2PioTransmitPurgeFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to discard any bytes of unsent data that remain in the transmit FIFO in the serial controller.


## -parameters




### -param PioTransmit 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method to create this object.


### -param BytesAlreadyTransmittedToHardware 
[in]
The number of bytes that have already been loaded into the transmit FIFO during the current PIO-transmit transaction. This parameter is the sum of all the bytes transferred in previous calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_write_buffer">EvtSerCx2PioTransmitWriteBuffer</a> event callback function that are part of this transaction.


## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

Your driver should implement an <i>EvtSerCx2PioTransmitPurgeFifo</i> function if the serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data. If your driver implements this function, it must also implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_drain_fifo">EvtSerCx2PioTransmitDrainFifo</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_cancel_drain_fifo">EvtSerCx2PioTransmitCancelDrainFifo</a> event callback functions.

SerCx2 initiates a PIO-transmit transaction in response to a write (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request from a client. If this request times out or is canceled before it completes, SerCx2 calls the <i>EvtSerCx2PioTransmitPurgeFifo</i> function, if it is implemented, to purge any unsent data that might remain the transmit FIFO.

After the transmit FIFO is purged, the <i>EvtSerCx2PioTransmitPurgeFifo</i> function must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitpurgefifocomplete">SerCx2PioTransmitPurgeFifoComplete</a> method to notify SerCx2 that the FIFO was purged, and SerCx2 then completes the write request.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265336(v=vs.85)">SerCx2 PIO-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioTransmitPurgeFifo</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioTransmitPurgeFifo</i> callback function that is named <code>MyPioTransmitPurgeFifo</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO  MyPioTransmitPurgeFifo;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyPioTransmitPurgeFifo(
    SERCX2PIOTRANSMIT  PioTransmit,
    ULONG  BytesAlreadyTransmittedToHardware

    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_PURGE_FIFO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitpurgefifocomplete">SerCx2PioTransmitPurgeFifoComplete</a>
 

 

