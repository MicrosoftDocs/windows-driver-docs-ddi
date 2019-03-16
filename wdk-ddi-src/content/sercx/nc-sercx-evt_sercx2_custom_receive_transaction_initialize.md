---
UID: NC:sercx.EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE
title: EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE (sercx.h)
description: The EvtSerCx2CustomReceiveTransactionInitialize event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller hardware to perform a new custom-receive transaction.
old-location: serports\evtsercx2customreceivetransactioninitialize.htm
tech.root: serports
ms.assetid: B3C23236-2A35-456A-B461-AEC688ACA5B7
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2CustomReceiveTransactionInitialize, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE callback, EvtSerCx2CustomReceiveTransactionInitialize, EvtSerCx2CustomReceiveTransactionInitialize callback function [Serial Ports], serports.evtsercx2customreceivetransactioninitialize
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
- EvtSerCx2CustomReceiveTransactionInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE callback function


## -description


The <i>EvtSerCx2CustomReceiveTransactionInitialize</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller hardware to perform a new custom-receive transaction.


## -parameters




### -param CustomReceiveTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive-transaction object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


### -param Mdl [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> that describes the memory pages that are spanned by the read buffer for the custom-receive transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.


### -param Offset [in]

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## -returns



None.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> call that creates the custom-receive object.

Your driver should implement an <i>EvtSerCx2CustomReceiveTransactionInitialize</i> function if it needs to initialize the serial controller and associated hardware in preparation for a new custom-receive transaction. SerCx2 calls this function, if it is implemented, before starting the custom-receive transaction. In response to this call, the serial controller driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265252">SerCx2CustomReceiveTransactionInitializeComplete</a> method to notify SerCx2 after the initialization is finished.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2CustomReceiveTransactionInitialize</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2CustomReceiveTransactionInitialize</i> callback function that is named <code>MyCustomReceiveTransactionInitialize</code>, use the <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE  MyCustomReceiveTransactionInitialize;</pre>
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
  MyCustomReceiveTransactionInitialize(
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
The <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_INITIALIZE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265252">SerCx2CustomReceiveTransactionInitializeComplete</a>
 

 

