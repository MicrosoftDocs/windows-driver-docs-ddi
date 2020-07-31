---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION (sercx.h)
description: The EvtSerCx2SystemDmaTransmitCleanupTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller state after a system-DMA-transmit transaction ends.
old-location: serports\evtsercx2systemdmatransmitcleanuptransaction.htm
tech.root: serports
ms.assetid: DAC33D61-F85C-43A7-9F4D-AA31F8CA4430
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION callback function"]
ms.keywords: 2/EvtSerCx2SystemDmaTransmitCleanupTransaction, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION callback, EvtSerCx2SystemDmaTransmitCleanupTransaction, EvtSerCx2SystemDmaTransmitCleanupTransaction callback function [Serial Ports], serports.evtsercx2systemdmatransmitcleanuptransaction
f1_keywords:
 - "sercx/EvtSerCx2SystemDmaTransmitCleanupTransaction"
 - "EvtSerCx2SystemDmaTransmitCleanupTransaction"
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
- EvtSerCx2SystemDmaTransmitCleanupTransaction
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION callback function


## -description


The <i>EvtSerCx2SystemDmaTransmitCleanupTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller state after a system-DMA-transmit transaction ends.


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method to create this object.


## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

Your serial controller driver should implement an <i>EvtSerCx2SystemDmaTransmitCleanupTransaction</i> function if it needs to clean up the serial controller state at the end of a system-DMA-transmit transaction. SerCx2 calls this function, if it is implemented, after a system-DMA-transmit transaction ends. In response to the <i>EvtSerCx2SystemDmaTransmitCleanupTransaction</i> call, the serial controller driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcleanuptransactioncomplete">SerCx2SystemDmaTransmitCleanupTransactionComplete</a> method to notify SerCx2 after the clean-up work is done.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaTransmitCleanupTransaction</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaTransmitCleanupTransaction</i> callback function that is named <code>MySystemDmaTransmitCleanupTransaction</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION  MySystemDmaTransmitCleanupTransaction;</pre>
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
  MySystemDmaTransmitCleanupTransaction(
    SERCX2SYSTEMDMATRANSMIT  SystemDmaTransmit
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CLEANUP_TRANSACTION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcleanuptransactioncomplete">SerCx2SystemDmaTransmitCleanupTransactionComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>
 

 

