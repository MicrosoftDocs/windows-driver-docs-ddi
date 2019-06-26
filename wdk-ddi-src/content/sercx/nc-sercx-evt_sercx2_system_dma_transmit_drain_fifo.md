---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO (sercx.h)
description: The EvtSerCx2SystemDmaTransmitDrainFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to drain the transmit FIFO in the serial controller hardware.
old-location: serports\evtsercx2systemdmatransmitdrainfifo.htm
tech.root: serports
ms.assetid: 796A6C4B-0C7E-43C5-88BC-C03DAA3869A6
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2SystemDmaTransmitDrainFifo, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO callback, EvtSerCx2SystemDmaTransmitDrainFifo, EvtSerCx2SystemDmaTransmitDrainFifo callback function [Serial Ports], serports.evtsercx2systemdmatransmitdrainfifo
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2SystemDmaTransmitDrainFifo
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO callback function


## -description


The <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to drain the transmit FIFO in the serial controller hardware.


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method to create this object.


## -returns



None.




## -remarks



Your serial controller driver can, as an option, implement this function. If your driver implements this function, it must also implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a> event callback functions. A driver that implements these functions registers them in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

SerCx2 calls the <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function, if it is implemented, to drain the transmit FIFO in the serial controller hardware at the end of a system-DMA-transmit transaction. This function makes sure that any data bytes that remain in the FIFO are transmitted to the serially connected peripheral device. After the last byte is transmitted from the FIFO, the <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmatransmitdrainfifocomplete">SerCx2SystemDmaTransmitDrainFifoComplete</a> method to notify SerCx2.

If the serial controller driver implements an <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function, SerCx2 does not complete a pending write (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>) request until the driver calls <b>SerCx2SystemDmaTransmitDrainFifoComplete</b>.

If your serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data, your driver should implement an <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function. Otherwise, SerCx2 cannot confirm that the transmit FIFO has drained before the pending write request is completed. Instead, SerCx2 completes this request after the last byte in the write buffer is written to the transmit FIFO. There can be no guarantee that data written to the transmit FIFO will be transmitted without a significant delay. Any data that remains in the FIFO after the write request is completed might be lost before it can be transmitted to the serially connected peripheral device. This unexpected data loss in a successfully completed write request can create reliability problems for the peripheral driver.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> callback function that is named <code>MySystemDmaTransmitDrainFifo</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO  MySystemDmaTransmitDrainFifo;</pre>
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
  MySystemDmaTransmitDrainFifo(
    SERCX2SYSTEMDMATRANSMIT  SystemDmaTransmit
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2systemdmatransmitdrainfifocomplete">SerCx2SystemDmaTransmitDrainFifoComplete</a>
 

 

