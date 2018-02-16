---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO
author: windows-driver-content
description: The EvtSerCx2SystemDmaTransmitPurgeFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to discard any bytes of unsent data that remain in the transmit FIFO in the serial controller hardware.
old-location: serports\evtsercx2systemdmatransmitpurgefifo.htm
old-project: serports
ms.assetid: 79BD2B77-E99A-4CFA-9F7B-AFC984D5F0B3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2systemdmatransmitpurgefifo, EvtSerCx2SystemDmaTransmitPurgeFifo callback function [Serial Ports], EvtSerCx2SystemDmaTransmitPurgeFifo, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO, 2/EvtSerCx2SystemDmaTransmitPurgeFifo
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
-	EvtSerCx2SystemDmaTransmitPurgeFifo
product: Windows
targetos: Windows
req.typenames: "*PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR"
req.product: Windows 10 or later.
---

# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO callback


## -description


The <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to discard any bytes of unsent data that remain in the transmit FIFO in the serial controller hardware.


## -prototype


````
EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO EvtSerCx2SystemDmaTransmitPurgeFifo;

VOID EvtSerCx2SystemDmaTransmitPurgeFifo(
  _In_ SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit,
  _In_ ULONG                   BytesAlreadyTransmittedToHardware
)
{ ... }
````


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method to create this object.


### -param BytesAlreadyTransmittedToHardware [in]

The number of bytes that have already been loaded into the transmit FIFO during the current system-DMA-transmit transaction.


## -returns



None.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

Your driver should implement an <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> function if the serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data. If your driver implements this function, it must also implement the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo.md">EvtSerCx2SystemDmaTransmitDrainFifo</a> and <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo.md">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a> event callback functions.

If a pending write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request times out or is canceled, SerCx2 might need to terminate the current system-DMA transaction before it finishes. After the transaction is terminated, SerCx2 calls the <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> function, if it is implemented.

The <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> function halts the transfer of data from the write buffer to the transmit FIFO, and discards any previously transferred data that remains in the FIFO. After the transmit transaction is terminated, the driver must call the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitpurgefifocomplete.md">SerCx2SystemDmaTransmitPurgeFifoComplete</a> method to notify SerCx2 that the FIFO was purged, and SerCx2 then completes the write request.

For more information, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaTransmitPurgeFifo</i> callback function that is named <code>MySystemDmaTransmitPurgeFifo</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO  MySystemDmaTransmitPurgeFifo;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MySystemDmaTransmitPurgeFifo(
    SERCX2SYSTEMDMATRANSMIT  SystemDmaTransmit,
    ULONG BytesAlreadyTransmittedToHardware
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo.md">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo.md">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>



<a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="..\sercx\nf-sercx-sercx2systemdmatransmitpurgefifocomplete.md">SerCx2SystemDmaTransmitPurgeFifoComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SYSTEM_DMA_TRANSMIT_PURGE_FIFO callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

