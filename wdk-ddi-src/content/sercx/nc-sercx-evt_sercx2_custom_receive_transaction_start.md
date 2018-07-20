---
UID: NC:sercx.EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START
title: EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START
author: windows-driver-content
description: The EvtSerCx2CustomReceiveTransactionStart event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-receive transaction.
old-location: serports\evtsercx2customreceivetransactionstart.htm
tech.root: serports
ms.assetid: F90250CC-EDBF-4DB7-B889-4BF6325FB0CD
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: 2/EvtSerCx2CustomReceiveTransactionStart, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START callback, EvtSerCx2CustomReceiveTransactionStart, EvtSerCx2CustomReceiveTransactionStart callback function [Serial Ports], serports.evtsercx2customreceivetransactionstart
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	2.0\Sercx.h
api_name:
-	EvtSerCx2CustomReceiveTransactionStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START callback function


## -description


The <i>EvtSerCx2CustomReceiveTransactionStart</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-receive transaction.


## -parameters




### -param CustomReceiveTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive-transaction object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


### -param Request [in]

A handle to the framework request object associated with the custom-receive transaction. The driver is responsible for completing this request. This request might not be the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> request sent by the client, and thus the serial controller driver should not try to use this request to access the read buffer. This request is primarily used for cancellation, completion, and queue forwarding (if needed). To access the read buffer for the client's read request, use the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.


### -param Mdl [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> that describes the memory pages that are spanned by the read buffer for the custom-receive transaction. The scatter/gather list for the data transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.


### -param Offset [in]

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## -returns



None.




## -remarks



Your serial controller driver must implement this function if it creates a custom-receive-transaction object. The driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> call that creates this object.

After SerCx2 calls the <i>EvtSerCx2CustomReceiveTransactionStart</i> function, the serial controller driver initiates the transaction by programming the custom data-transfer mechanism to move data from the receive FIFO in the serial controller hardware to the buffer in the read request. Unless the request can be completed immediately, before the <i>EvtSerCx2CustomReceiveTransactionStart</i> function returns, the driver must call a method such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to mark the request as cancelable.

After the <i>EvtSerCx2CustomReceiveTransactionStart</i> function starts the transaction, SerCx2 periodically calls the <a href="https://msdn.microsoft.com/B0B08257-E867-4E22-949E-555AD44C2DDE">EvtSerCx2CustomReceiveTransactionQueryProgress</a> event callback function to monitor progress made by the serial controller driver in performing this transaction. After the transaction finishes and the driver completes the pending read request, SerCx2 calls the <a href="https://msdn.microsoft.com/72AF3D52-D109-42A7-9F25-14A3F5EDC94A">EvtSerCx2CustomReceiveTransactionCleanup</a> event callback function, if the driver implements this function.

If the serial controller driver implements an <a href="https://msdn.microsoft.com/B3C23236-2A35-456A-B461-AEC688ACA5B7">EvtSerCx2CustomReceiveTransactionInitialize</a> event callback function, SerCx2 calls this function before calling the <i>EvtSerCx2CustomReceiveTransactionStart</i> function. Just before the <i>EvtSerCx2CustomReceiveTransactionStart</i> call, and after the <i>EvtSerCx2CustomReceiveTransactionInitialize</i> call returns, SerCx2 starts the timer that detects whether the read request times out. For more information, see the discussion of total time-outs in  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>.

If the custom data-transfer mechanism is a bus-master DMA device, the <i>EvtSerCx2CustomReceiveTransactionStart</i> function can call a method such as <a href="https://msdn.microsoft.com/library/windows/hardware/hh451182">WdfDmaTransactionInitializeUsingOffset</a> to initiate a DMA transaction that uses the read buffer described by the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.

If the request object identified by the <i>Request</i> parameter contains storage for a private context, this storage might be uninitialized the first time the serial controller driver accesses the context. On first access, the driver typically should fill the context with zeros, and then, if needed, explicitly set any fields in the context that require nonzero initial values.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2CustomReceiveTransactionStart</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2CustomReceiveTransactionStart</i> callback function that is named <code>MyCustomReceiveTransactionStart</code>, use the <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START  MyCustomReceiveTransactionStart;</pre>
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
  MyCustomReceiveTransactionStart(
    SERCX2CUSTOMRECEIVETRANSACTION  CustomReceiveTransaction,
    WDFREQUEST  Request,
    PMDL  Mdl,
    ULONG  Offset,
    ULONG  Length
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451182">WdfDmaTransactionInitializeUsingOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>
 

 

