---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION
title: EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION
description: The EvtSerCx2PioReceiveCleanupTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller's hardware state after a PIO-receive transaction ends.
old-location: serports\evtsercx2pioreceivecleanuptransaction.htm
tech.root: serports
ms.assetid: 2CFCF5D9-23F8-4571-972A-0BE48EB2D046
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2PioReceiveCleanupTransaction, EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION, EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION callback, EvtSerCx2PioReceiveCleanupTransaction, EvtSerCx2PioReceiveCleanupTransaction callback function [Serial Ports], serports.evtsercx2pioreceivecleanuptransaction
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
-	EvtSerCx2PioReceiveCleanupTransaction
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION callback function


## -description


The <i>EvtSerCx2PioReceiveCleanupTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller's hardware state after a PIO-receive transaction ends.


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> method to create this object.


## -returns



None.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> method that creates the PIO-receive object.

Your serial controller driver should implement an <i>EvtSerCx2PioReceiveCleanupTransaction</i> function if it needs to clean up the serial controller state at the end of a PIO-receive transaction. SerCx2 calls this function, if it is implemented, after a PIO-receive transaction ends. In response to the <i>EvtSerCx2PioReceiveCleanupTransaction</i> call, the serial controller driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265263">SerCx2PioReceiveCleanupTransactionComplete</a> method to notify SerCx2 after the clean-up work is done.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioReceiveCleanupTransaction</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioReceiveCleanupTransaction</i> callback function that is named <code>MyPioReceiveCleanupTransaction</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION  MyPioReceiveCleanupTransaction;</pre>
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
  MyPioReceiveCleanupTransaction(
    SERCX2PIORECEIVE  PioReceive
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_CLEANUP_TRANSACTION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265263">SerCx2PioReceiveCleanupTransactionComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a>
 

 

